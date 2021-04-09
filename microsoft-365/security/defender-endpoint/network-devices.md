---
title: Individuazione dei dispositivi di rete e gestione delle vulnerabilità
description: I suggerimenti per la sicurezza e il rilevamento delle vulnerabilità sono ora disponibili per i sistemi operativi di commutatori, router, controller WLAN e firewall.
keywords: dispositivi di rete, rilevamento delle vulnerabilità dei dispositivi di rete, sistemi operativi di commutatori, router, controller WLAN e firewall
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d0ae82c2e284235d96531c04dc2240063d4e4183
ms.sourcegitcommit: dcc6bfd228ca9070975ce9eb14574e084f9ed92c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2021
ms.locfileid: "51657042"
---
# <a name="network-device-discovery-and-vulnerability-management"></a><span data-ttu-id="11fdd-104">Individuazione dei dispositivi di rete e gestione delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="11fdd-104">Network device discovery and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="11fdd-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="11fdd-105">**Applies to:**</span></span>

- [<span data-ttu-id="11fdd-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="11fdd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="11fdd-107">Gestione di minacce e vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="11fdd-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="11fdd-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="11fdd-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="11fdd-109">**L'analisi e la gestione dei dispositivi di rete sono attualmente in anteprima pubblica**</span><span class="sxs-lookup"><span data-stu-id="11fdd-109">**Scanning and managing network devices is currently in public preview**</span></span><br>
> <span data-ttu-id="11fdd-110">Questa versione di anteprima viene fornita senza un contratto di servizio e non è consigliata per i carichi di lavoro di produzione.</span><span class="sxs-lookup"><span data-stu-id="11fdd-110">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="11fdd-111">Alcune funzionalità potrebbero non essere supportate o avere funzionalità vincolate.</span><span class="sxs-lookup"><span data-stu-id="11fdd-111">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="11fdd-112">Per altre informazioni, vedi [Funzionalità di anteprima di Microsoft Defender per Endpoint.](preview.md)</span><span class="sxs-lookup"><span data-stu-id="11fdd-112">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

><span data-ttu-id="11fdd-113">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="11fdd-113">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="11fdd-114">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="11fdd-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="11fdd-115">Le funzionalità di individuazione della rete sono disponibili nella sezione **Inventario** dispositivi del Centro sicurezza Microsoft 365 e delle console di Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="11fdd-115">Network discovery capabilities are available in the **Device inventory** section of the Microsoft 365 security center and Microsoft Defender Security Center consoles.</span></span>  

<span data-ttu-id="11fdd-116">Un dispositivo Microsoft Defender for Endpoint designato verrà usato in ogni segmento di rete per eseguire analisi periodiche autenticate di dispositivi di rete preconfigurati.</span><span class="sxs-lookup"><span data-stu-id="11fdd-116">A designated Microsoft Defender for Endpoint device will be used on each network segment to perform periodic authenticated scans of preconfigured network devices.</span></span> <span data-ttu-id="11fdd-117">Una volta individuate, le funzionalità di gestione delle minacce e delle vulnerabilità di Defender for Endpoint forniscono flussi di lavoro integrati per proteggere commutatori, router, controller WLAN, firewall e gateway VPN individuati.</span><span class="sxs-lookup"><span data-stu-id="11fdd-117">Once discovered, Defender for Endpoint’s threat and vulnerability management capabilities provide integrated workflows to secure discovered switches, routers, WLAN controllers, firewalls, and VPN gateways.</span></span>  

<span data-ttu-id="11fdd-118">Una volta individuati e classificati i dispositivi di rete, gli amministratori della sicurezza saranno in grado di ricevere i consigli più recenti sulla sicurezza ed esaminare le vulnerabilità individuate di recente nei dispositivi di rete distribuiti nelle organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="11fdd-118">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>

## <a name="approach"></a><span data-ttu-id="11fdd-119">Approccio</span><span class="sxs-lookup"><span data-stu-id="11fdd-119">Approach</span></span>

<span data-ttu-id="11fdd-120">I dispositivi di rete non vengono gestiti come endpoint standard poiché Defender for Endpoint non dispone di un sensore incorporato nei dispositivi di rete stessi.</span><span class="sxs-lookup"><span data-stu-id="11fdd-120">Network devices are not managed as standard endpoints since Defender for Endpoint doesn’t have a sensor built into the network devices themselves.</span></span> <span data-ttu-id="11fdd-121">Questi tipi di dispositivi richiedono un approccio senza agenti in cui un'analisi remota oquisterà le informazioni necessarie dai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="11fdd-121">These types of devices require an agentless approach where a remote scan will obtain the necessary information from the devices.</span></span> <span data-ttu-id="11fdd-122">A seconda della topologia e delle caratteristiche di rete, un singolo dispositivo o alcuni dispositivi onboarded in Microsoft Defender for Endpoint eseguiranno analisi autenticate dei dispositivi di rete utilizzando SNMP (sola lettura).</span><span class="sxs-lookup"><span data-stu-id="11fdd-122">Depending on the network topology and characteristics, a single device or a few devices onboarded to Microsoft Defender for Endpoint will perform authenticated scans of network devices using SNMP (read-only).</span></span>

<span data-ttu-id="11fdd-123">Ci saranno due tipi di dispositivi da tenere presenti:</span><span class="sxs-lookup"><span data-stu-id="11fdd-123">There will be two types of devices to keep in mind:</span></span>

- <span data-ttu-id="11fdd-124">**Dispositivo di valutazione:** un dispositivo già onboarded che userai per analizzare i dispositivi di rete.</span><span class="sxs-lookup"><span data-stu-id="11fdd-124">**Assessment device**: A device that's already onboarded that you'll use to scan the network devices.</span></span>
- <span data-ttu-id="11fdd-125">**Dispositivi di rete:** i dispositivi di rete che si prevede di analizzare e eseguire l'onboard.</span><span class="sxs-lookup"><span data-stu-id="11fdd-125">**Network devices**: The network devices you plan to scan and onboard.</span></span>

### <a name="vulnerability-management-for-network-devices"></a><span data-ttu-id="11fdd-126">Gestione delle vulnerabilità per i dispositivi di rete</span><span class="sxs-lookup"><span data-stu-id="11fdd-126">Vulnerability management for network devices</span></span> 

<span data-ttu-id="11fdd-127">Una volta individuati e classificati i dispositivi di rete, gli amministratori della sicurezza saranno in grado di ricevere i consigli più recenti sulla sicurezza ed esaminare le vulnerabilità individuate di recente nei dispositivi di rete distribuiti nelle organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="11fdd-127">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>  

## <a name="operating-systems-that-are-supported"></a><span data-ttu-id="11fdd-128">Sistemi operativi supportati</span><span class="sxs-lookup"><span data-stu-id="11fdd-128">Operating systems that are supported</span></span>

<span data-ttu-id="11fdd-129">Attualmente sono supportati i seguenti sistemi operativi:</span><span class="sxs-lookup"><span data-stu-id="11fdd-129">The following operating systems are currently supported:</span></span>

- <span data-ttu-id="11fdd-130">Cisco IOS, IOS-XE, NX-OS</span><span class="sxs-lookup"><span data-stu-id="11fdd-130">Cisco IOS, IOS-XE, NX-OS</span></span>
- <span data-ttu-id="11fdd-131">Juniper JUNOS</span><span class="sxs-lookup"><span data-stu-id="11fdd-131">Juniper JUNOS</span></span>
- <span data-ttu-id="11fdd-132">HPE ArubaOS, software di commutazione di procura</span><span class="sxs-lookup"><span data-stu-id="11fdd-132">HPE ArubaOS, Procurve Switch Software</span></span>
- <span data-ttu-id="11fdd-133">Palo Alto Networks PAN-OS</span><span class="sxs-lookup"><span data-stu-id="11fdd-133">Palo Alto Networks PAN-OS</span></span>

<span data-ttu-id="11fdd-134">Nel tempo verranno aggiunti altri fornitori di rete e sistema operativo, in base ai dati raccolti dall'utilizzo dei clienti.</span><span class="sxs-lookup"><span data-stu-id="11fdd-134">More networking vendors and OS will be added over time, based on data gathered from customer usage.</span></span> <span data-ttu-id="11fdd-135">Pertanto, si consiglia di configurare tutti i dispositivi di rete, anche se non sono specificati in questo elenco.</span><span class="sxs-lookup"><span data-stu-id="11fdd-135">Therefore, you are encouraged to configure all your network devices, even if they’re not specified in this list.</span></span>

## <a name="how-to-get-started"></a><span data-ttu-id="11fdd-136">Come iniziare</span><span class="sxs-lookup"><span data-stu-id="11fdd-136">How to get started</span></span>

<span data-ttu-id="11fdd-137">Il primo passaggio consiste nel selezionare un dispositivo che eseguirà le analisi di rete autenticate.</span><span class="sxs-lookup"><span data-stu-id="11fdd-137">Your first step is to select a device that will perform the authenticated network scans.</span></span>

1. <span data-ttu-id="11fdd-138">Decidi un dispositivo defender per endpoint onboarded (client o server) che dispone di una connessione di rete alla porta di gestione per i dispositivi di rete che vuoi analizzare.</span><span class="sxs-lookup"><span data-stu-id="11fdd-138">Decide on a Defender for Endpoint onboarded device (client or server) that has a network connection to the management port for the network devices you plan on scanning.</span></span> 

2. <span data-ttu-id="11fdd-139">Il traffico SNMP tra il dispositivo di valutazione Defender for Endpoint e i dispositivi di rete di destinazione deve essere consentito (ad esempio, dal firewall).</span><span class="sxs-lookup"><span data-stu-id="11fdd-139">SNMP traffic between the Defender for Endpoint assessment device and the targeted network devices must be allowed (for example, by the Firewall).</span></span>

3. <span data-ttu-id="11fdd-140">Decidi quali dispositivi di rete verranno valutati per le vulnerabilità (ad esempio, un commutatore Cisco o un firewall Palo Alto Networks).</span><span class="sxs-lookup"><span data-stu-id="11fdd-140">Decide which network devices will be assessed for vulnerabilities (for example: a Cisco switch or a Palo Alto Networks firewall).</span></span>  

4. <span data-ttu-id="11fdd-141">Assicurati che la sola lettura SNMP sia abilitata in tutti i dispositivi di rete configurati per consentire al dispositivo di valutazione Defender for Endpoint di eseguire query sui dispositivi di rete configurati.</span><span class="sxs-lookup"><span data-stu-id="11fdd-141">Make sure SNMP read-only is enabled on all configured network devices to allow the Defender for Endpoint assessment device to query the configured network devices.</span></span> <span data-ttu-id="11fdd-142">La scrittura SNMP non è necessaria per le funzionalità appropriate di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="11fdd-142">‘SNMP write’ isn't needed for the proper functionality of this feature.</span></span>

5. <span data-ttu-id="11fdd-143">Ottenere gli indirizzi IP dei dispositivi di rete da analizzare (o le subnet in cui questi dispositivi vengono distribuiti).</span><span class="sxs-lookup"><span data-stu-id="11fdd-143">Obtain the IP addresses of the network devices to be scanned (or the subnets where these devices are deployed).</span></span>

6. <span data-ttu-id="11fdd-144">Ottenere le credenziali SNMP dei dispositivi di rete (ad esempio: Community String, noAuthNoPriv, authNoPriv, authPriv).</span><span class="sxs-lookup"><span data-stu-id="11fdd-144">Obtain the SNMP credentials of the network devices (for example: Community String, noAuthNoPriv, authNoPriv, authPriv).</span></span> <span data-ttu-id="11fdd-145">Sarà necessario fornire le credenziali durante la configurazione di un nuovo processo di valutazione.</span><span class="sxs-lookup"><span data-stu-id="11fdd-145">You’ll be required to provide the credentials when configuring a new assessment job.</span></span>  

7. <span data-ttu-id="11fdd-146">Configurazione del client proxy: non è necessaria alcuna configurazione aggiuntiva oltre ai requisiti di Defender per il proxy del dispositivo endpoint.</span><span class="sxs-lookup"><span data-stu-id="11fdd-146">Proxy client configuration: No extra configuration is required other than the Defender for Endpoint device proxy requirements.</span></span>

8. <span data-ttu-id="11fdd-147">Per consentire l'autenticazione e il corretto funzionamento dello scanner di rete, è essenziale aggiungere i domini/URL seguenti:</span><span class="sxs-lookup"><span data-stu-id="11fdd-147">To allow the network scanner to be authenticated and work properly, it's essential that you add the following domains/URLs:</span></span>

    - <span data-ttu-id="11fdd-148">login.windows.net</span><span class="sxs-lookup"><span data-stu-id="11fdd-148">login.windows.net</span></span>  
    - <span data-ttu-id="11fdd-149">\*.securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="11fdd-149">\*.securitycenter.windows.com</span></span>
    - <span data-ttu-id="11fdd-150">login.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="11fdd-150">login.microsoftonline.com</span></span>
    - <span data-ttu-id="11fdd-151">\*.blob.core.windows.net/networkscannerstable/ \*</span><span class="sxs-lookup"><span data-stu-id="11fdd-151">\*.blob.core.windows.net/networkscannerstable/ \*</span></span>

    <span data-ttu-id="11fdd-152">Nota: non tutti gli URL non sono specificati nell'elenco documentato di Defender for Endpoint della raccolta dati consentita.</span><span class="sxs-lookup"><span data-stu-id="11fdd-152">Note: Not all URLs are not specified in the Defender for Endpoint documented list of allowed data collection.</span></span>

## <a name="permissions"></a><span data-ttu-id="11fdd-153">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="11fdd-153">Permissions</span></span>

<span data-ttu-id="11fdd-154">Per configurare i processi di valutazione, è necessaria l'opzione di autorizzazione utente seguente: **Gestire le impostazioni di sicurezza nel Centro sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="11fdd-154">To configure assessment jobs, the following user permission option is required: **Manage security settings in Security Center**.</span></span> <span data-ttu-id="11fdd-155">Per trovare l'autorizzazione, accedere a **Impostazioni**  >  **Ruoli.**</span><span class="sxs-lookup"><span data-stu-id="11fdd-155">You can find the permission by going to **Settings** > **Roles**.</span></span> <span data-ttu-id="11fdd-156">Per ulteriori informazioni, vedere [Create and manage roles for role-based access control](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="11fdd-156">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

## <a name="install-the-network-scanner"></a><span data-ttu-id="11fdd-157">Installare lo scanner di rete</span><span class="sxs-lookup"><span data-stu-id="11fdd-157">Install the network scanner</span></span>

1. <span data-ttu-id="11fdd-158">Passare a **Impostazioni di sicurezza di Microsoft 365** Processi di valutazione degli  >    >  **endpoint**  >   (in "Valutazioni di rete").</span><span class="sxs-lookup"><span data-stu-id="11fdd-158">Go to **Microsoft 365 security** > **Settings** > **Endpoints** > **Assessment jobs** (under 'Network assessments').</span></span>
    1. <span data-ttu-id="11fdd-159">In Microsoft Defender Security Center passare a Impostazioni > processi di valutazione.</span><span class="sxs-lookup"><span data-stu-id="11fdd-159">In the Microsoft Defender Security Center, go to Settings > Assessment jobs page.</span></span>

2. <span data-ttu-id="11fdd-160">Scarica lo scanner di rete e installalo nel dispositivo di valutazione Defender for Endpoint designato.</span><span class="sxs-lookup"><span data-stu-id="11fdd-160">Download the network scanner and install it on the designated Defender for Endpoint assessment device.</span></span>

![Pulsante Scarica scanner](images/assessment-jobs-download-scanner.png)

## <a name="network-scanner-installation--registration"></a><span data-ttu-id="11fdd-162">Installazione scanner di rete & registrazione</span><span class="sxs-lookup"><span data-stu-id="11fdd-162">Network scanner installation & registration</span></span>

<span data-ttu-id="11fdd-163">Il processo di accesso può essere completato sul dispositivo di valutazione designato stesso o su qualsiasi altro dispositivo (ad esempio, il dispositivo client personale).</span><span class="sxs-lookup"><span data-stu-id="11fdd-163">The signing-in process can be completed on the designated assessment device itself or any other device (for example, your personal client device).</span></span>

<span data-ttu-id="11fdd-164">Per completare il processo di registrazione dello scanner di rete:</span><span class="sxs-lookup"><span data-stu-id="11fdd-164">To complete the network scanner registration process:</span></span>

1. <span data-ttu-id="11fdd-165">Copiare e seguire l'URL visualizzato nella riga di comando e utilizzare il codice di installazione fornito per completare il processo di registrazione.</span><span class="sxs-lookup"><span data-stu-id="11fdd-165">Copy and follow the URL that appears on the command line and use the provided installation code to complete the registration process.</span></span>
    - <span data-ttu-id="11fdd-166">Nota: potrebbe essere necessario modificare le impostazioni del prompt dei comandi per poter copiare l'URL.</span><span class="sxs-lookup"><span data-stu-id="11fdd-166">Note: You may need to change Command Prompt settings to be able to copy the URL.</span></span>

2. <span data-ttu-id="11fdd-167">Immetti il codice e accedi con un account Microsoft con l'autorizzazione Defender for Endpoint denominata "Gestire le impostazioni di sicurezza nel Centro sicurezza".</span><span class="sxs-lookup"><span data-stu-id="11fdd-167">Enter the code and sign in using a Microsoft account that has the Defender for Endpoint permission called "Manage security settings in Security Center."</span></span>

3. <span data-ttu-id="11fdd-168">Al termine, verrà visualizzato un messaggio di conferma dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="11fdd-168">When finished, you should see a message confirming you have signed in.</span></span>

## <a name="configure-a-new-assessment-job"></a><span data-ttu-id="11fdd-169">Configurare un nuovo processo di valutazione</span><span class="sxs-lookup"><span data-stu-id="11fdd-169">Configure a new assessment job</span></span>  

<span data-ttu-id="11fdd-170">Nella pagina Processi di valutazione in **Impostazioni** selezionare **Aggiungi processo di valutazione di rete.**</span><span class="sxs-lookup"><span data-stu-id="11fdd-170">In the Assessment jobs page in **Settings**, select **Add network assessment job**.</span></span> <span data-ttu-id="11fdd-171">Segui il processo di configurazione per scegliere i dispositivi di rete da analizzare regolarmente e aggiungere all'inventario dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="11fdd-171">Follow the set-up process to choose network devices to be scanned regularly and added to the device inventory.</span></span>

<span data-ttu-id="11fdd-172">Per impedire la duplicazione dei dispositivi nell'inventario dei dispositivi di rete, assicurati che ogni indirizzo IP sia configurato una sola volta tra più dispositivi di valutazione.</span><span class="sxs-lookup"><span data-stu-id="11fdd-172">To prevent device duplication in the network device inventory, make sure each IP address is configured only once across multiple assessment devices.</span></span>

![Pulsante Aggiungi processo di valutazione di rete](images/assessment-jobs-add.png)

<span data-ttu-id="11fdd-174">Aggiunta dei passaggi di un processo di valutazione della rete:</span><span class="sxs-lookup"><span data-stu-id="11fdd-174">Adding a network assessment job steps:</span></span>

1. <span data-ttu-id="11fdd-175">Scegliere il nome di un processo di valutazione e il "dispositivo di valutazione" in cui è stato installato lo scanner di rete.</span><span class="sxs-lookup"><span data-stu-id="11fdd-175">Choose an ‘Assessment job’ name and the ‘Assessment device’ on which the network scanner was installed.</span></span> <span data-ttu-id="11fdd-176">Questo dispositivo eseguirà le analisi periodiche autenticate.</span><span class="sxs-lookup"><span data-stu-id="11fdd-176">This device will perform the periodic authenticated scans.</span></span> 
2. <span data-ttu-id="11fdd-177">Aggiungere gli indirizzi IP dei dispositivi di rete di destinazione da analizzare (o le subnet in cui questi dispositivi vengono distribuiti).</span><span class="sxs-lookup"><span data-stu-id="11fdd-177">Add IP addresses of target network devices to be scanned (or the subnets where these devices are deployed).</span></span> 
3. <span data-ttu-id="11fdd-178">Aggiungere le credenziali SNMP necessarie dei dispositivi di rete di destinazione.</span><span class="sxs-lookup"><span data-stu-id="11fdd-178">Add required SNMP credentials of the target network devices.</span></span> 
4. <span data-ttu-id="11fdd-179">Salvare il processo di valutazione della rete appena configurato per avviare l'analisi periodica della rete.</span><span class="sxs-lookup"><span data-stu-id="11fdd-179">Save the newly configured network assessment job to start the periodic network scan.</span></span> 

### <a name="scan-and-add-network-devices"></a><span data-ttu-id="11fdd-180">Analizzare e aggiungere dispositivi di rete</span><span class="sxs-lookup"><span data-stu-id="11fdd-180">Scan and add network devices</span></span>

<span data-ttu-id="11fdd-181">Durante il processo di configurazione, è possibile eseguire un'analisi di test una sola volta per verificare che:</span><span class="sxs-lookup"><span data-stu-id="11fdd-181">During the set-up process, you can perform a one time test scan to verify that:</span></span>

- <span data-ttu-id="11fdd-182">Esiste una connettività tra il dispositivo di valutazione Defender for Endpoint e i dispositivi di rete di destinazione configurati.</span><span class="sxs-lookup"><span data-stu-id="11fdd-182">There is connectivity between the Defender for Endpoint assessment device and the configured target network devices.</span></span>
- <span data-ttu-id="11fdd-183">Le credenziali SNMP configurate sono corrette.</span><span class="sxs-lookup"><span data-stu-id="11fdd-183">The configured SNMP credentials are correct.</span></span>

<span data-ttu-id="11fdd-184">Ogni dispositivo di valutazione può supportare fino a 1.500 analisi degli indirizzi IP riusciti.</span><span class="sxs-lookup"><span data-stu-id="11fdd-184">Each assessment device can support up to 1,500 successful IP addresses scan.</span></span> <span data-ttu-id="11fdd-185">Ad esempio, se si analizzano 10 subnet diverse in cui solo 100 indirizzi IP restituiscono risultati positivi, sarà possibile analizzare 1.400 indirizzi IP aggiuntivi da altre subnet sullo stesso dispositivo di valutazione.</span><span class="sxs-lookup"><span data-stu-id="11fdd-185">For example, if you scan 10 different subnets where only 100 IP addresses return successful results, you will be able to scan 1,400 IP additional addresses from other subnets on the same assessment device.</span></span>  

<span data-ttu-id="11fdd-186">Se sono presenti più intervalli di indirizzi IP/subnet da analizzare, la visualizzazione dei risultati dell'analisi di test avrà alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="11fdd-186">If there are multiple IP address ranges/subnets to scan, the test scan results will take several minutes to show up.</span></span> <span data-ttu-id="11fdd-187">Sarà disponibile un'analisi di test per un massimo di 1.024 indirizzi.</span><span class="sxs-lookup"><span data-stu-id="11fdd-187">A test scan will be available for up to 1,024 addresses.</span></span>

<span data-ttu-id="11fdd-188">Una volta visualizzati i risultati, puoi scegliere quali dispositivi verranno inclusi nell'analisi periodica.</span><span class="sxs-lookup"><span data-stu-id="11fdd-188">Once the results show up, you can choose which devices will be included in the periodic scan.</span></span> <span data-ttu-id="11fdd-189">Se si ignora la visualizzazione dei risultati dell'analisi, tutti gli indirizzi IP configurati verranno aggiunti al processo di valutazione della rete (indipendentemente dalla risposta del dispositivo).</span><span class="sxs-lookup"><span data-stu-id="11fdd-189">If you skip viewing the scan results, all configured IP addresses will be added to the network assessment job (regardless of the device’s response).</span></span> <span data-ttu-id="11fdd-190">È inoltre possibile esportare i risultati dell'analisi.</span><span class="sxs-lookup"><span data-stu-id="11fdd-190">The scan results can also be exported.</span></span>

## <a name="device-inventory"></a><span data-ttu-id="11fdd-191">Inventario dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="11fdd-191">Device inventory</span></span>

<span data-ttu-id="11fdd-192">I nuovi dispositivi individuati verranno visualizzati nella nuova **scheda Dispositivi di** rete nella pagina **Inventario** dispositivi.</span><span class="sxs-lookup"><span data-stu-id="11fdd-192">Newly discovered devices will be shown under the new **Network devices** tab in the **Device inventory** page.</span></span> <span data-ttu-id="11fdd-193">L'aggiunta di un processo di valutazione può richiedere fino a due ore prima dell'aggiornamento dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="11fdd-193">It may take up to two hours after adding an assessment job until the devices are updated.</span></span>

![Sezione Dispositivi di rete nell'inventario dei dispositivi](images/assessment-jobs-device-inventory.png)

## <a name="troubleshooting"></a><span data-ttu-id="11fdd-195">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="11fdd-195">Troubleshooting</span></span>

### <a name="network-scanner-installation-has-failed"></a><span data-ttu-id="11fdd-196">Installazione scanner di rete non riuscita</span><span class="sxs-lookup"><span data-stu-id="11fdd-196">Network scanner installation has failed</span></span>

<span data-ttu-id="11fdd-197">Verificare che gli URL necessari siano aggiunti ai domini consentiti nelle impostazioni del firewall.</span><span class="sxs-lookup"><span data-stu-id="11fdd-197">Verify that the required URLs are added to the allowed domains in your firewall settings.</span></span> <span data-ttu-id="11fdd-198">Verificare inoltre che le impostazioni proxy siano configurate come descritto in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="11fdd-198">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md)</span></span>

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a><span data-ttu-id="11fdd-199">La Microsoft.com/devicelogin web non è stata visualizzata</span><span class="sxs-lookup"><span data-stu-id="11fdd-199">The Microsoft.com/devicelogin web page did not show up</span></span>

<span data-ttu-id="11fdd-200">Verificare che gli URL necessari siano aggiunti ai domini consentiti nel firewall.</span><span class="sxs-lookup"><span data-stu-id="11fdd-200">Verify that the required URLs are added to the allowed domains in your firewall.</span></span> <span data-ttu-id="11fdd-201">Verificare inoltre che le impostazioni proxy siano configurate come descritto in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span><span class="sxs-lookup"><span data-stu-id="11fdd-201">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a><span data-ttu-id="11fdd-202">I dispositivi di rete non vengono visualizzati nell'inventario dei dispositivi dopo diverse ore</span><span class="sxs-lookup"><span data-stu-id="11fdd-202">Network devices are not shown in the device inventory after several hours</span></span>

<span data-ttu-id="11fdd-203">I risultati dell'analisi devono essere aggiornati alcune ore dopo l'analisi iniziale eseguita dopo il completamento della configurazione del processo di valutazione.</span><span class="sxs-lookup"><span data-stu-id="11fdd-203">The scan results should be updated a few hours after the initial scan that took place after completing the assessment job configuration.</span></span>

<span data-ttu-id="11fdd-204">Se i dispositivi non sono ancora visualizzati, verificare che il servizio 'MdatpNetworkScanService' sia in esecuzione nei dispositivi di valutazione, in cui è stato installato lo scanner di rete, ed eseguire un'analisi "Esegui" nella configurazione del processo di valutazione pertinente.</span><span class="sxs-lookup"><span data-stu-id="11fdd-204">If devices are still not shown, verify that the service ‘MdatpNetworkScanService’ is running on your assessment devices, on which you installed the network scanner, and perform a “Run scan” in the relevant assessment job configuration.</span></span>  

<span data-ttu-id="11fdd-205">Se non si ottengono ancora risultati dopo 5 minuti, riavviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="11fdd-205">If you still don’t get results after 5 minutes, restart the service.</span></span>  

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a><span data-ttu-id="11fdd-206">L'ora dell'ultima volta per i dispositivi è più lunga di 24 ore</span><span class="sxs-lookup"><span data-stu-id="11fdd-206">Devices last seen time is longer than 24 hours</span></span>

<span data-ttu-id="11fdd-207">Verificare che lo scanner sia in esecuzione correttamente.</span><span class="sxs-lookup"><span data-stu-id="11fdd-207">Validate that the scanner is running properly.</span></span> <span data-ttu-id="11fdd-208">Passare quindi alla definizione di analisi e selezionare "Esegui test".</span><span class="sxs-lookup"><span data-stu-id="11fdd-208">Then go to the scan definition and select “Run test.”</span></span> <span data-ttu-id="11fdd-209">Controllare quali messaggi di errore vengono restituiti dagli indirizzi IP pertinenti.</span><span class="sxs-lookup"><span data-stu-id="11fdd-209">Check what error messages are returning from the relevant IP addresses.</span></span>

### <a name="required-threat-and-vulnerability-management-user-permission"></a><span data-ttu-id="11fdd-210">Autorizzazione utente necessaria per la gestione delle minacce e delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="11fdd-210">Required threat and vulnerability management user permission</span></span>

<span data-ttu-id="11fdd-211">Registrazione completata con un errore: "Sembra che non si disponga di autorizzazioni sufficienti per l'aggiunta di un nuovo agente.</span><span class="sxs-lookup"><span data-stu-id="11fdd-211">Registration finished with an error: "It looks like you don't have sufficient permissions for adding a new agent.</span></span> <span data-ttu-id="11fdd-212">L'autorizzazione necessaria è "Gestire le impostazioni di sicurezza nel Centro sicurezza".</span><span class="sxs-lookup"><span data-stu-id="11fdd-212">The required permission is 'Manage security settings in Security Center'."</span></span>

<span data-ttu-id="11fdd-213">Premere un tasto qualsiasi per uscire.</span><span class="sxs-lookup"><span data-stu-id="11fdd-213">Press any key to exit.</span></span>

<span data-ttu-id="11fdd-214">Chiedere all'amministratore di sistema di assegnare le autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="11fdd-214">Ask your system administrator to assign you the required permissions.</span></span> <span data-ttu-id="11fdd-215">In alternativa, chiedere a un altro membro rilevante di aiutarti con il processo di accesso fornendo loro il codice di accesso e il collegamento.</span><span class="sxs-lookup"><span data-stu-id="11fdd-215">Alternately, ask another relevant member to help you with the sign-in process by providing them with the sign-in code and link.</span></span>

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a><span data-ttu-id="11fdd-216">Il processo di registrazione non riesce utilizzando il collegamento fornito nella riga di comando nel processo di registrazione</span><span class="sxs-lookup"><span data-stu-id="11fdd-216">Registration process fails using provided link in the command line in registration process</span></span>

<span data-ttu-id="11fdd-217">Prova un browser diverso o copia il collegamento e il codice di accesso in un altro dispositivo.</span><span class="sxs-lookup"><span data-stu-id="11fdd-217">Try a different browser or copy the sign-in link and code to a different device.</span></span>

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a><span data-ttu-id="11fdd-218">Testo troppo piccolo o non in grado di copiare testo dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="11fdd-218">Text too small or can’t copy text from command line</span></span>

<span data-ttu-id="11fdd-219">Modifica le impostazioni della riga di comando nel dispositivo per consentire la copia e la modifica delle dimensioni del testo.</span><span class="sxs-lookup"><span data-stu-id="11fdd-219">Change command-line settings on your device to allow copying and change text size.</span></span>

## <a name="related-articles"></a><span data-ttu-id="11fdd-220">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="11fdd-220">Related articles</span></span>

- [<span data-ttu-id="11fdd-221">Inventario dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="11fdd-221">Device inventory</span></span>](machines-view-overview.md)
- [<span data-ttu-id="11fdd-222">Configurare le funzionalità avanzate</span><span class="sxs-lookup"><span data-stu-id="11fdd-222">Configure advanced features</span></span>](advanced-features.md)
