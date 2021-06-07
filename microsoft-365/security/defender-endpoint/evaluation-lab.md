---
title: Laboratorio di valutazione di Microsoft Defender for Endpoint
description: Informazioni sulle funzionalità di Microsoft Defender for Endpoint, eseguire simulazioni di attacco e vedere come impedisce, rileva e correggere le minacce.
keywords: valutare Microsoft Defender for Endpoint, valutazione, lab, simulazione, Windows 10, Windows Server 2019, laboratorio di valutazione
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c785dbb759afe77b14f41985b9f451a4ec52e29f
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778234"
---
# <a name="microsoft-defender-for-endpoint-evaluation-lab"></a><span data-ttu-id="0297a-104">Laboratorio di valutazione di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0297a-104">Microsoft Defender for Endpoint evaluation lab</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0297a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0297a-105">**Applies to:**</span></span>
- [<span data-ttu-id="0297a-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="0297a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="0297a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0297a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0297a-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="0297a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0297a-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="0297a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="0297a-110">L'esecuzione di una valutazione completa del prodotto per la sicurezza può essere un processo complesso che richiede una configurazione complessa dell'ambiente e del dispositivo prima di poter effettivamente eseguire una simulazione di attacco end-to-end.</span><span class="sxs-lookup"><span data-stu-id="0297a-110">Conducting a comprehensive security product evaluation can be a complex process requiring cumbersome environment and device configuration before an end-to-end attack simulation can actually be done.</span></span> <span data-ttu-id="0297a-111">L'aggiunta alla complessità è la sfida di tenere traccia dei casi in cui le attività di simulazione, gli avvisi e i risultati si riflettono durante la valutazione.</span><span class="sxs-lookup"><span data-stu-id="0297a-111">Adding to the complexity is the challenge of tracking where the simulation activities, alerts, and results are reflected during the evaluation.</span></span>

<span data-ttu-id="0297a-112">Il laboratorio di valutazione di Microsoft Defender for Endpoint è progettato per eliminare le complessità della configurazione di dispositivi e ambienti, in modo da concentrarti sulla valutazione delle funzionalità della piattaforma, sull'esecuzione di simulazioni e sulla visualizzazione delle funzionalità di prevenzione, rilevamento e correzione in azione.</span><span class="sxs-lookup"><span data-stu-id="0297a-112">The Microsoft Defender for Endpoint evaluation lab is designed to eliminate the complexities of device and environment configuration so that you can  focus on evaluating the capabilities of the platform, running simulations, and seeing the prevention, detection, and remediation features in action.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUM]

<span data-ttu-id="0297a-113">Con l'esperienza di configurazione semplificata, puoi concentrarti sull'esecuzione di scenari di test personalizzati e sulle simulazioni predefinite per vedere le prestazioni di Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="0297a-113">With the simplified set-up experience, you can focus on running your own test scenarios and the pre-made simulations to see how Defender for Endpoint performs.</span></span> 

<span data-ttu-id="0297a-114">Avrai accesso completo alle potenti funzionalità della piattaforma, ad esempio indagini automatizzate, ricerca avanzata e analisi delle minacce, consentendoti di testare lo stack di protezione completo che Defender for Endpoint offre.</span><span class="sxs-lookup"><span data-stu-id="0297a-114">You'll have full access to the powerful capabilities of the platform such as automated investigations, advanced hunting, and threat analytics, allowing you to test the comprehensive protection stack that Defender for Endpoint offers.</span></span> 

<span data-ttu-id="0297a-115">È possibile aggiungere dispositivi Windows 10 o Windows Server 2019 preconfigurato per installare le versioni più recenti del sistema operativo e i componenti di sicurezza più recenti e Office 2019 Standard.</span><span class="sxs-lookup"><span data-stu-id="0297a-115">You can add Windows 10 or Windows Server 2019 devices that come pre-configured to have the latest OS versions and the right security components in place as well as Office 2019 Standard installed.</span></span>

<span data-ttu-id="0297a-116">Puoi anche installare simulatori di minacce.</span><span class="sxs-lookup"><span data-stu-id="0297a-116">You can also install threat simulators.</span></span> <span data-ttu-id="0297a-117">Defender for Endpoint ha collaborato con le principali piattaforme di simulazione delle minacce del settore per aiutarti a testare le funzionalità di Defender for Endpoint senza dover uscire dal portale.</span><span class="sxs-lookup"><span data-stu-id="0297a-117">Defender for Endpoint has partnered with industry leading threat simulation platforms to help you test out the Defender for Endpoint capabilities without having to leave the portal.</span></span>

 <span data-ttu-id="0297a-118">Installa il simulatore preferito, esegui scenari all'interno del laboratorio di valutazione e scopri immediatamente le prestazioni della piattaforma, il tutto comodamente disponibile senza costi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="0297a-118">Install your preferred simulator, run scenarios within the evaluation lab, and instantly see how the platform performs - all conveniently available at no extra cost to you.</span></span> <span data-ttu-id="0297a-119">Avrai anche un comodo accesso a un'ampia gamma di simulazioni a cui puoi accedere ed eseguire dal catalogo delle simulazioni.</span><span class="sxs-lookup"><span data-stu-id="0297a-119">You'll also have convenient access to wide array of simulations which you can access and run from the simulations catalog.</span></span>
    

## <a name="before-you-begin"></a><span data-ttu-id="0297a-120">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="0297a-120">Before you begin</span></span>
<span data-ttu-id="0297a-121">Dovrai soddisfare i requisiti [](minimum-requirements.md#licensing-requirements) di licenza o avere accesso di prova a Microsoft Defender for Endpoint per accedere al laboratorio di valutazione.</span><span class="sxs-lookup"><span data-stu-id="0297a-121">You'll need to fulfill the [licensing requirements](minimum-requirements.md#licensing-requirements) or have trial access to Microsoft Defender for Endpoint to access the evaluation lab.</span></span>

<span data-ttu-id="0297a-122">È necessario disporre delle autorizzazioni Di gestione **delle impostazioni di** sicurezza per:</span><span class="sxs-lookup"><span data-stu-id="0297a-122">You must have **Manage security settings** permissions to:</span></span>
- <span data-ttu-id="0297a-123">Creare il lab</span><span class="sxs-lookup"><span data-stu-id="0297a-123">Create the lab</span></span>
- <span data-ttu-id="0297a-124">Creare dispositivi</span><span class="sxs-lookup"><span data-stu-id="0297a-124">Create devices</span></span>
- <span data-ttu-id="0297a-125">Reimpostare la password</span><span class="sxs-lookup"><span data-stu-id="0297a-125">Reset password</span></span>
- <span data-ttu-id="0297a-126">Creare simulazioni</span><span class="sxs-lookup"><span data-stu-id="0297a-126">Create simulations</span></span> 
 
<span data-ttu-id="0297a-127">Se è stato abilitato il controllo di accesso basato sui ruoli (RBAC) e è stato creato almeno un gruppo di computer, gli utenti devono avere accesso a Tutti i gruppi di computer.</span><span class="sxs-lookup"><span data-stu-id="0297a-127">If you enabled role-based access control (RBAC) and created at least a one machine group, users must have access to All machine groups.</span></span>

<span data-ttu-id="0297a-128">Per ulteriori informazioni, vedere [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="0297a-128">For more information, see [Create and manage roles](user-roles.md).</span></span>

<span data-ttu-id="0297a-129">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="0297a-129">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0297a-130">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="0297a-130">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink)


## <a name="get-started-with-the-lab"></a><span data-ttu-id="0297a-131">Introduzione al lab</span><span class="sxs-lookup"><span data-stu-id="0297a-131">Get started with the lab</span></span>
<span data-ttu-id="0297a-132">Puoi accedere al lab dal menu.</span><span class="sxs-lookup"><span data-stu-id="0297a-132">You can access the lab from the menu.</span></span> <span data-ttu-id="0297a-133">Nel menu di spostamento seleziona **Valutazione ed esercitazioni > lab di valutazione.**</span><span class="sxs-lookup"><span data-stu-id="0297a-133">In the navigation menu, select **Evaluation and tutorials > Evaluation lab**.</span></span>

![Immagine del laboratorio di valutazione nel menu](images/evaluation-lab-menu.png)

>[!NOTE]
>- <span data-ttu-id="0297a-135">A seconda del tipo di struttura dell'ambiente selezionato, i dispositivi saranno disponibili per il numero di ore specificato a partire dal giorno dell'attivazione.</span><span class="sxs-lookup"><span data-stu-id="0297a-135">Depending the type of environment structure you select, devices will be available for the specified number of hours from the day of activation.</span></span>
>- <span data-ttu-id="0297a-136">Viene eseguito il provisioning di ogni ambiente con un set limitato di dispositivi di test.</span><span class="sxs-lookup"><span data-stu-id="0297a-136">Each environment is provisioned with a limited set of test devices.</span></span> <span data-ttu-id="0297a-137">Dopo aver usato i dispositivi di cui è stato eseguito il provisioning e li hai eliminati, puoi richiedere altri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0297a-137">When you've used up the provisioned devices and have deleted them, you can request for more devices.</span></span> 
>- <span data-ttu-id="0297a-138">È possibile richiedere risorse lab una volta al mese.</span><span class="sxs-lookup"><span data-stu-id="0297a-138">You can request for lab resources once a month.</span></span> 

<span data-ttu-id="0297a-139">Hai già un lab?</span><span class="sxs-lookup"><span data-stu-id="0297a-139">Already have a lab?</span></span> <span data-ttu-id="0297a-140">Assicurati di abilitare i nuovi simulatori di minacce e di avere dispositivi attivi.</span><span class="sxs-lookup"><span data-stu-id="0297a-140">Make sure to enable the new threat simulators and have active devices.</span></span>

## <a name="setup-the-evaluation-lab"></a><span data-ttu-id="0297a-141">Configurare il laboratorio di valutazione</span><span class="sxs-lookup"><span data-stu-id="0297a-141">Setup the evaluation lab</span></span>

1. <span data-ttu-id="0297a-142">Nel riquadro di spostamento, selezionare **Valutazione ed esercitazioni**  >  **Laboratorio di** valutazione, quindi **selezionare Setup lab.**</span><span class="sxs-lookup"><span data-stu-id="0297a-142">In the navigation pane, select **Evaluation and tutorials** > **Evaluation lab**, then select **Setup lab**.</span></span>

    ![Immagine della pagina di benvenuto del laboratorio di valutazione](images/evaluation-lab-setup.png)

2. <span data-ttu-id="0297a-144">A seconda delle esigenze di valutazione, puoi scegliere di configurare un ambiente con meno dispositivi per un periodo più lungo o più dispositivi per un periodo più breve.</span><span class="sxs-lookup"><span data-stu-id="0297a-144">Depending on your evaluation needs, you can choose to setup an environment with fewer devices for a longer period or more devices for a shorter period.</span></span> <span data-ttu-id="0297a-145">Seleziona la configurazione lab preferita e quindi seleziona **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0297a-145">Select your preferred lab configuration then select **Next**.</span></span>

    ![Immagine delle opzioni di configurazione lab](images/lab-creation-page.png) 


3. <span data-ttu-id="0297a-147">(Facoltativo) Puoi scegliere di installare simulatori di minacce nel lab.</span><span class="sxs-lookup"><span data-stu-id="0297a-147">(Optional) You can choose to install threat simulators in the lab.</span></span> 

    ![Immagine dell'agente simulatori di installazione](images/install-agent.png)

    >[!IMPORTANT]
    ><span data-ttu-id="0297a-149">Dovrai prima accettare e fornire il consenso alle condizioni e alle dichiarazioni di condivisione delle informazioni.</span><span class="sxs-lookup"><span data-stu-id="0297a-149">You'll first need to accept and provide consent to the terms and information sharing statements.</span></span> 

4. <span data-ttu-id="0297a-150">Selezionare l'agente di simulazione delle minacce che si desidera utilizzare e immettere i dettagli.</span><span class="sxs-lookup"><span data-stu-id="0297a-150">Select the threat simulation agent you'd like to use and enter your details.</span></span> <span data-ttu-id="0297a-151">Puoi anche scegliere di installare simulatori di minacce in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="0297a-151">You can also choose to install threat simulators at a later time.</span></span> <span data-ttu-id="0297a-152">Se si sceglie di installare gli agenti di simulazione delle minacce durante la configurazione del lab, sarà possibile installarli comodamente nei dispositivi aggiunti.</span><span class="sxs-lookup"><span data-stu-id="0297a-152">If you choose to install threat simulation agents during the lab setup, you'll enjoy the benefit of having them conveniently installed on the devices you add.</span></span>  
    
    ![Immagine della pagina di riepilogo](images/lab-setup-summary.png)

5.  <span data-ttu-id="0297a-154">Esaminare il riepilogo e selezionare **Setup lab**.</span><span class="sxs-lookup"><span data-stu-id="0297a-154">Review the summary and select **Setup lab**.</span></span>  

<span data-ttu-id="0297a-155">Al termine del processo di installazione del lab, è possibile aggiungere dispositivi ed eseguire simulazioni.</span><span class="sxs-lookup"><span data-stu-id="0297a-155">After the lab setup process is complete, you can add devices and run simulations.</span></span> 


## <a name="add-devices"></a><span data-ttu-id="0297a-156">Aggiungere dispositivi</span><span class="sxs-lookup"><span data-stu-id="0297a-156">Add devices</span></span>
<span data-ttu-id="0297a-157">Quando aggiungi un dispositivo all'ambiente, Defender for Endpoint configura un dispositivo ben configurato con i dettagli di connessione.</span><span class="sxs-lookup"><span data-stu-id="0297a-157">When you add a device to your environment, Defender for Endpoint sets up a well-configured device with connection details.</span></span> <span data-ttu-id="0297a-158">È possibile aggiungere Windows 10 o Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0297a-158">You can add Windows 10 or Windows Server 2019 devices.</span></span>

<span data-ttu-id="0297a-159">Il dispositivo verrà configurato con la versione più aggiornata del sistema operativo e Office 2019 Standard e con altre app come Java, Python e SysIntenals.</span><span class="sxs-lookup"><span data-stu-id="0297a-159">The device will be configured with the most up-to-date version of the OS and Office 2019 Standard as well as other apps such as Java, Python, and SysIntenals.</span></span> 

<span data-ttu-id="0297a-160">Se hai scelto di aggiungere un simulatore di minacce durante la configurazione del lab, tutti i dispositivi avranno l'agente simulatore di minacce installato nei dispositivi che aggiungi.</span><span class="sxs-lookup"><span data-stu-id="0297a-160">If you chose to add a threat simulator during the lab setup, all devices will have the threat simulator agent installed in the devices that you add.</span></span>

<span data-ttu-id="0297a-161">Il dispositivo verrà automaticamente onboarded nel tenant con i componenti di sicurezza Windows consigliati attivati e in modalità di controllo, senza alcun impegno da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0297a-161">The device will automatically be onboarded to your tenant with the recommended Windows security components turned on and in audit mode - with no effort on your side.</span></span> 

<span data-ttu-id="0297a-162">I componenti di sicurezza seguenti sono preconfigurato nei dispositivi di test:</span><span class="sxs-lookup"><span data-stu-id="0297a-162">The following security components are pre-configured in the test devices:</span></span>

- [<span data-ttu-id="0297a-163">Riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="0297a-163">Attack surface reduction</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)
- [<span data-ttu-id="0297a-164">Blocco al primo avvistamento</span><span class="sxs-lookup"><span data-stu-id="0297a-164">Block at first sight</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
- [<span data-ttu-id="0297a-165">Accesso controllato alle cartelle</span><span class="sxs-lookup"><span data-stu-id="0297a-165">Controlled folder access</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)
- [<span data-ttu-id="0297a-166">Protezione dagli exploit</span><span class="sxs-lookup"><span data-stu-id="0297a-166">Exploit protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/enable-exploit-protection)
- [<span data-ttu-id="0297a-167">Protezione di rete</span><span class="sxs-lookup"><span data-stu-id="0297a-167">Network protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
- [<span data-ttu-id="0297a-168">Rilevamento di applicazioni potenzialmente indesiderate</span><span class="sxs-lookup"><span data-stu-id="0297a-168">Potentially unwanted application detection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [<span data-ttu-id="0297a-169">Protezione basata sul cloud</span><span class="sxs-lookup"><span data-stu-id="0297a-169">Cloud-delivered protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="0297a-170">Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="0297a-170">Microsoft Defender SmartScreen</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview)

>[!NOTE]
> <span data-ttu-id="0297a-171">Antivirus Microsoft Defender sarà attivata (non in modalità di controllo).</span><span class="sxs-lookup"><span data-stu-id="0297a-171">Microsoft Defender Antivirus will be on (not in audit mode).</span></span> <span data-ttu-id="0297a-172">Se Antivirus Microsoft Defender l'esecuzione della simulazione, puoi disattivare la protezione in tempo reale nel dispositivo tramite Sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="0297a-172">If Microsoft Defender Antivirus blocks you from running your simulation, you can turn off real-time protection on the device through Windows Security.</span></span> <span data-ttu-id="0297a-173">Per ulteriori informazioni, vedere [Configure always-on protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="0297a-173">For more information, see [Configure always-on protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="0297a-174">Le impostazioni di analisi automatizzate dipendono dalle impostazioni del tenant.</span><span class="sxs-lookup"><span data-stu-id="0297a-174">Automated investigation settings will be dependent on tenant settings.</span></span> <span data-ttu-id="0297a-175">Verrà configurata per essere semiautomizzata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0297a-175">It will be configured to be semi-automated by default.</span></span> <span data-ttu-id="0297a-176">Per ulteriori informazioni, vedere [Overview of Automated investigations](automated-investigations.md).</span><span class="sxs-lookup"><span data-stu-id="0297a-176">For more information, see [Overview of Automated investigations](automated-investigations.md).</span></span>

>[!NOTE]
><span data-ttu-id="0297a-177">La connessione ai dispositivi di test viene eseguita tramite RDP.</span><span class="sxs-lookup"><span data-stu-id="0297a-177">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="0297a-178">Verificare che le impostazioni del firewall consentano le connessioni RDP.</span><span class="sxs-lookup"><span data-stu-id="0297a-178">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="0297a-179">Nel dashboard seleziona **Aggiungi dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="0297a-179">From the dashboard, select **Add device**.</span></span> 

2. <span data-ttu-id="0297a-180">Scegli il tipo di dispositivo da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="0297a-180">Choose the type of device to add.</span></span> <span data-ttu-id="0297a-181">È possibile scegliere di aggiungere Windows 10 o Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0297a-181">You can choose to add Windows 10 or Windows Server 2019.</span></span>

    ![Immagine della configurazione del lab con le opzioni del dispositivo](images/add-machine-options.png)


    >[!NOTE]
    ><span data-ttu-id="0297a-183">Se si verifica un problema durante il processo di creazione del dispositivo, verrà inviata una notifica e sarà necessario inviare una nuova richiesta.</span><span class="sxs-lookup"><span data-stu-id="0297a-183">If something goes wrong with the device creation process, you'll be notified and you'll need to submit a new request.</span></span> <span data-ttu-id="0297a-184">Se la creazione del dispositivo ha esito negativo, non verrà conteggiata rispetto alla quota complessiva consentita.</span><span class="sxs-lookup"><span data-stu-id="0297a-184">If the device creation fails, it will not be counted against the overall allowed quota.</span></span> 

3. <span data-ttu-id="0297a-185">Vengono visualizzati i dettagli della connessione.</span><span class="sxs-lookup"><span data-stu-id="0297a-185">The connection details are displayed.</span></span> <span data-ttu-id="0297a-186">Seleziona **Copia** per salvare la password per il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0297a-186">Select **Copy** to save the password for the device.</span></span>

    >[!NOTE]
    ><span data-ttu-id="0297a-187">La password viene visualizzata una sola volta.</span><span class="sxs-lookup"><span data-stu-id="0297a-187">The password is only displayed once.</span></span> <span data-ttu-id="0297a-188">Assicurati di salvarlo per un uso successivo.</span><span class="sxs-lookup"><span data-stu-id="0297a-188">Be sure to save it for later use.</span></span>

    ![Immagine del dispositivo aggiunto con i dettagli di connessione](images/add-machine-eval-lab.png)

4. <span data-ttu-id="0297a-190">Viene avviata la configurazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0297a-190">Device set up begins.</span></span> <span data-ttu-id="0297a-191">Questa operazione può richiedere fino a circa 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="0297a-191">This can take up to approximately 30 minutes.</span></span> 

5. <span data-ttu-id="0297a-192">Vedi lo stato dei dispositivi di test, i livelli di rischio e esposizione e lo stato delle installazioni di simulatori selezionando la **scheda** Dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0297a-192">See the status of test devices, the risk and exposure levels, and the status of simulator installations by selecting the **Devices** tab.</span></span> 

    ![Scheda Immagine dei dispositivi](images/machines-tab.png)
    

    > [!TIP]
    > <span data-ttu-id="0297a-194">Nella colonna **Stato simulatore** puoi passare il mouse sull'icona delle informazioni per conoscere lo stato di installazione di un agente.</span><span class="sxs-lookup"><span data-stu-id="0297a-194">In the **Simulator status** column, you can hover over the information icon to know the installation status of an agent.</span></span>

## <a name="request-for-more-devices"></a><span data-ttu-id="0297a-195">Richiesta di altri dispositivi</span><span class="sxs-lookup"><span data-stu-id="0297a-195">Request for more devices</span></span>
<span data-ttu-id="0297a-196">Quando tutti i dispositivi esistenti vengono usati ed eliminati, puoi richiedere altri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0297a-196">When all existing devices are used and deleted, you can request for more devices.</span></span> <span data-ttu-id="0297a-197">È possibile richiedere risorse lab una volta al mese.</span><span class="sxs-lookup"><span data-stu-id="0297a-197">You can request for lab resources once a month.</span></span> 


1. <span data-ttu-id="0297a-198">Nel dashboard del lab di valutazione seleziona **Richiedi altri dispositivi.**</span><span class="sxs-lookup"><span data-stu-id="0297a-198">From the evaluation lab dashboard, select **Request for more devices**.</span></span>

   ![Immagine della richiesta di altri dispositivi](images/request-more-devices.png)

2. <span data-ttu-id="0297a-200">Scegliere la configurazione.</span><span class="sxs-lookup"><span data-stu-id="0297a-200">Choose your configuration.</span></span> 
3. <span data-ttu-id="0297a-201">Inviare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="0297a-201">Submit the request.</span></span> 

<span data-ttu-id="0297a-202">Quando la richiesta viene inviata correttamente, vedrai un banner di conferma verde e la data dell'ultimo invio.</span><span class="sxs-lookup"><span data-stu-id="0297a-202">When the request is submitted successfully you'll see a green confirmation banner and the date of the last submission.</span></span>
 
<span data-ttu-id="0297a-203">Puoi trovare lo stato della richiesta nella **scheda Azioni** utente, che verrà approvata in poche ore.</span><span class="sxs-lookup"><span data-stu-id="0297a-203">You can find the status of your request in the **User Actions** tab, which will be approved in a matter of hours.</span></span>

<span data-ttu-id="0297a-204">Una volta approvati, i dispositivi richiesti verranno aggiunti alla configurazione del lab e potrai creare altri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0297a-204">When approved, the requested devices will be added to your lab set up and you’ll be able to create more devices.</span></span> 


> [!TIP]
> <span data-ttu-id="0297a-205">Per ottenere di più dal lab, non dimenticare di consultare la libreria di simulazioni.</span><span class="sxs-lookup"><span data-stu-id="0297a-205">To get more out of your lab, don’t forget to check out our simulations library.</span></span>

## <a name="simulate-attack-scenarios"></a><span data-ttu-id="0297a-206">Simulare scenari di attacco</span><span class="sxs-lookup"><span data-stu-id="0297a-206">Simulate attack scenarios</span></span>
<span data-ttu-id="0297a-207">Usa i dispositivi di test per eseguire le tue simulazioni di attacco connettendoti a essi.</span><span class="sxs-lookup"><span data-stu-id="0297a-207">Use the test devices to run your own attack simulations by connecting to them.</span></span> 

<span data-ttu-id="0297a-208">Puoi simulare scenari di attacco usando:</span><span class="sxs-lookup"><span data-stu-id="0297a-208">You can simulate attack scenarios using:</span></span>
- <span data-ttu-id="0297a-209">Scenari di attacco ["Fai da te"](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="0297a-209">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="0297a-210">Simulatori di minacce</span><span class="sxs-lookup"><span data-stu-id="0297a-210">Threat simulators</span></span>

<span data-ttu-id="0297a-211">È inoltre possibile utilizzare [la ricerca avanzata per](advanced-hunting-query-language.md) eseguire query sui dati e [sull'analisi](threat-analytics.md) delle minacce per visualizzare i report sulle minacce emergenti.</span><span class="sxs-lookup"><span data-stu-id="0297a-211">You can also use [Advanced hunting](advanced-hunting-query-language.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="0297a-212">Scenari di attacco fai-da-te</span><span class="sxs-lookup"><span data-stu-id="0297a-212">Do-it-yourself attack scenarios</span></span>
<span data-ttu-id="0297a-213">Se stai cercando una simulazione predefinita, puoi usare i nostri scenari di attacco "Fai da [te".](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="0297a-213">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="0297a-214">Questi script sono sicuri, documentati e facili da usare.</span><span class="sxs-lookup"><span data-stu-id="0297a-214">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="0297a-215">Questi scenari rifletteranno le funzionalità di Defender for Endpoint e illustrano l'esperienza di analisi.</span><span class="sxs-lookup"><span data-stu-id="0297a-215">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>


>[!NOTE]
><span data-ttu-id="0297a-216">La connessione ai dispositivi di test viene eseguita tramite RDP.</span><span class="sxs-lookup"><span data-stu-id="0297a-216">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="0297a-217">Verificare che le impostazioni del firewall consentano le connessioni RDP.</span><span class="sxs-lookup"><span data-stu-id="0297a-217">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="0297a-218">Connessione al dispositivo ed esegui una simulazione di attacco selezionando **Connessione**.</span><span class="sxs-lookup"><span data-stu-id="0297a-218">Connect to your device and run an attack simulation by selecting **Connect**.</span></span> 

    ![Immagine del pulsante di connessione per i dispositivi di test](images/test-machine-table.png)

2. <span data-ttu-id="0297a-220">Salvare il file RDP e avviarlo selezionando **Connessione**.</span><span class="sxs-lookup"><span data-stu-id="0297a-220">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![Immagine della connessione desktop remoto](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="0297a-222">Se non si dispone di una copia della password salvata durante la configurazione iniziale, è possibile reimpostare la password selezionando Reimposta **password** dal menu: Immagine della password ![ di reimpostazione](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="0297a-222">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span><br>
    > <span data-ttu-id="0297a-223">Il dispositivo cambierà lo stato in "Esecuzione della reimpostazione della password", quindi ti verrà presentata la nuova password in pochi minuti.</span><span class="sxs-lookup"><span data-stu-id="0297a-223">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="0297a-224">Immetti la password visualizzata durante il passaggio di creazione del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0297a-224">Enter the password that was displayed during the device creation step.</span></span> 

   ![Immagine della finestra in cui immettere le credenziali](images/enter-password.png)

4. <span data-ttu-id="0297a-226">Esegui simulazioni di attacco fai-da-te nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0297a-226">Run Do-it-yourself attack simulations on the device.</span></span> 


### <a name="threat-simulator-scenarios"></a><span data-ttu-id="0297a-227">Scenari di simulatore di minacce</span><span class="sxs-lookup"><span data-stu-id="0297a-227">Threat simulator scenarios</span></span>
<span data-ttu-id="0297a-228">Se si è scelto di installare uno dei simulatori di minacce supportati durante la configurazione del lab, è possibile eseguire le simulazioni incorporate nei dispositivi del laboratorio di valutazione.</span><span class="sxs-lookup"><span data-stu-id="0297a-228">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span> 


<span data-ttu-id="0297a-229">L'esecuzione di simulazioni di minacce con piattaforme di terze parti è un buon modo per valutare le funzionalità di Microsoft Defender for Endpoint entro i limiti di un ambiente lab.</span><span class="sxs-lookup"><span data-stu-id="0297a-229">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
><span data-ttu-id="0297a-230">Prima di poter eseguire simulazioni, verificare che siano soddisfatti i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0297a-230">Before you can run simulations, ensure the following requirements are met:</span></span>
>- <span data-ttu-id="0297a-231">I dispositivi devono essere aggiunti al laboratorio di valutazione</span><span class="sxs-lookup"><span data-stu-id="0297a-231">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="0297a-232">I simulatori di minacce devono essere installati nel laboratorio di valutazione</span><span class="sxs-lookup"><span data-stu-id="0297a-232">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="0297a-233">Nel portale selezionare **Crea simulazione**.</span><span class="sxs-lookup"><span data-stu-id="0297a-233">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="0297a-234">Selezionare un simulatore di minacce.</span><span class="sxs-lookup"><span data-stu-id="0297a-234">Select a threat simulator.</span></span>

    ![Immagine della selezione del simulatore di minacce](images/select-simulator.png)

3. <span data-ttu-id="0297a-236">Scegliere una simulazione o esaminare la raccolta di simulazioni per esplorare le simulazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="0297a-236">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span> 

    <span data-ttu-id="0297a-237">Puoi accedere alla raccolta di simulazioni da:</span><span class="sxs-lookup"><span data-stu-id="0297a-237">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="0297a-238">Dashboard di valutazione principale nel riquadro **Panoramica simulazioni** o</span><span class="sxs-lookup"><span data-stu-id="0297a-238">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="0297a-239">Spostandosi dal riquadro di **spostamento** Valutazione ed esercitazioni  >  **Simulazione & esercitazioni**, quindi selezionare Catalogo **simulazioni**.</span><span class="sxs-lookup"><span data-stu-id="0297a-239">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="0297a-240">Seleziona i dispositivi in cui vuoi eseguire la simulazione.</span><span class="sxs-lookup"><span data-stu-id="0297a-240">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="0297a-241">Selezionare **Crea simulazione.**</span><span class="sxs-lookup"><span data-stu-id="0297a-241">Select **Create simulation**.</span></span>

6. <span data-ttu-id="0297a-242">Visualizzare lo stato di avanzamento di una simulazione selezionando la **scheda Simulazioni.** Visualizzare lo stato della simulazione, gli avvisi attivi e altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="0297a-242">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span> 

    ![Immagine della scheda simulazioni](images/simulations-tab.png)
    
<span data-ttu-id="0297a-244">Dopo aver eseguito le simulazioni, ti invitiamo a esaminare l'indicatore di stato del lab ed esplorare Microsoft Defender for Endpoint che ha attivato un'indagine e **una correzione automatizzate.**</span><span class="sxs-lookup"><span data-stu-id="0297a-244">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="0297a-245">Controlla le prove raccolte e analizzate dalla funzionalità.</span><span class="sxs-lookup"><span data-stu-id="0297a-245">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="0297a-246">Cercare le prove di attacco tramite la ricerca avanzata usando il linguaggio di query avanzato e la telemetria non elaborata e consultare alcune minacce a livello mondiale documentate in Threat analytics.</span><span class="sxs-lookup"><span data-stu-id="0297a-246">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>


## <a name="simulation-gallery"></a><span data-ttu-id="0297a-247">Raccolta simulazioni</span><span class="sxs-lookup"><span data-stu-id="0297a-247">Simulation gallery</span></span>
<span data-ttu-id="0297a-248">Microsoft Defender for Endpoint ha collaborato con diverse piattaforme di simulazione delle minacce per fornire un accesso pratico per testare le funzionalità della piattaforma direttamente dal portale.</span><span class="sxs-lookup"><span data-stu-id="0297a-248">Microsoft Defender for Endpoint has partnered with various threat simulation platforms to give you convenient access to test the capabilities of the platform right from the within the portal.</span></span> 

<span data-ttu-id="0297a-249">Per visualizzare tutte le simulazioni disponibili, accedere a **Simulazioni ed** esercitazioni  >  **Catalogo simulazioni** dal menu.</span><span class="sxs-lookup"><span data-stu-id="0297a-249">View all the available simulations by going to  **Simulations and tutorials** > **Simulations catalog**  from the menu.</span></span> 

<span data-ttu-id="0297a-250">Viene elencato un elenco degli agenti di simulazione delle minacce di terze parti supportati e nel catalogo vengono forniti tipi specifici di simulazioni e descrizioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="0297a-250">A list of supported third-party threat simulation agents are listed, and specific types of simulations along with detailed descriptions are provided on the catalog.</span></span> 

<span data-ttu-id="0297a-251">È possibile eseguire comodamente qualsiasi simulazione disponibile direttamente dal catalogo.</span><span class="sxs-lookup"><span data-stu-id="0297a-251">You can conveniently run any available simulation right from the catalog.</span></span>  


![Immagine del catalogo delle simulazioni](images/simulations-catalog.png)

<span data-ttu-id="0297a-253">Ogni simulazione include una descrizione approfondita dello scenario di attacco e riferimenti come le tecniche di attacco MITRE utilizzate e l'esempio di query di ricerca avanzata eseguite.</span><span class="sxs-lookup"><span data-stu-id="0297a-253">Each simulation comes with an in-depth description of the attack scenario and references such as the MITRE attack techniques used and sample Advanced hunting queries you run.</span></span>

<span data-ttu-id="0297a-254">**Esempi:** 
 ![ Immagine dei dettagli della descrizione della simulazione1](images/simulation-details-aiq.png)</span><span class="sxs-lookup"><span data-stu-id="0297a-254">**Examples:**
![Image of simulation description details1](images/simulation-details-aiq.png)</span></span>


![Immagine dei dettagli della descrizione della simulazione2](images/simulation-details-sb.png)


## <a name="evaluation-report"></a><span data-ttu-id="0297a-256">Report di valutazione</span><span class="sxs-lookup"><span data-stu-id="0297a-256">Evaluation report</span></span>
<span data-ttu-id="0297a-257">I report del lab riepilogano i risultati delle simulazioni eseguite sui dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0297a-257">The lab reports summarize the results of the simulations conducted on the devices.</span></span>

![Immagine del report di valutazione](images/eval-report.png)

<span data-ttu-id="0297a-259">A colpo d'occhio, potrai rapidamente vedere:</span><span class="sxs-lookup"><span data-stu-id="0297a-259">At a glance, you'll quickly be able to see:</span></span>
- <span data-ttu-id="0297a-260">Eventi imprevisti attivati</span><span class="sxs-lookup"><span data-stu-id="0297a-260">Incidents that were triggered</span></span>
- <span data-ttu-id="0297a-261">Avvisi generati</span><span class="sxs-lookup"><span data-stu-id="0297a-261">Generated alerts</span></span>
- <span data-ttu-id="0297a-262">Valutazioni a livello di esposizione</span><span class="sxs-lookup"><span data-stu-id="0297a-262">Assessments on exposure level</span></span> 
- <span data-ttu-id="0297a-263">Categorie di minacce osservate</span><span class="sxs-lookup"><span data-stu-id="0297a-263">Threat categories observed</span></span>
- <span data-ttu-id="0297a-264">Origini di rilevamento</span><span class="sxs-lookup"><span data-stu-id="0297a-264">Detection sources</span></span>
- <span data-ttu-id="0297a-265">Indagini automatizzate</span><span class="sxs-lookup"><span data-stu-id="0297a-265">Automated investigations</span></span>


## <a name="provide-feedback"></a><span data-ttu-id="0297a-266">Inviare feedback</span><span class="sxs-lookup"><span data-stu-id="0297a-266">Provide feedback</span></span>
<span data-ttu-id="0297a-267">Il tuo feedback ci aiuta a migliorare la protezione dell'ambiente dagli attacchi avanzati.</span><span class="sxs-lookup"><span data-stu-id="0297a-267">Your feedback helps us get better in protecting your environment from advanced attacks.</span></span> <span data-ttu-id="0297a-268">Condividere l'esperienza e le impression dalle funzionalità del prodotto e dai risultati della valutazione.</span><span class="sxs-lookup"><span data-stu-id="0297a-268">Share your experience and impressions from product capabilities and evaluation results.</span></span>

<span data-ttu-id="0297a-269">Facci sapere cosa ne pensi selezionando **Invia feedback.**</span><span class="sxs-lookup"><span data-stu-id="0297a-269">Let us know what you think, by selecting **Provide feedback**.</span></span>

![Immagine di fornire feedback](images/send-us-feedback-eval-lab.png)
