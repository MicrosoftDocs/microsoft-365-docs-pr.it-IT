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
ms.openlocfilehash: da15519211599bfc248c20c36cfab456c1661caa
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862068"
---
# <a name="network-device-discovery-and-vulnerability-management"></a><span data-ttu-id="c1d0f-104">Individuazione dei dispositivi di rete e gestione delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="c1d0f-104">Network device discovery and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c1d0f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c1d0f-105">**Applies to:**</span></span>

- [<span data-ttu-id="c1d0f-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="c1d0f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="c1d0f-107">Minaccia e gestione delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="c1d0f-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="c1d0f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c1d0f-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="c1d0f-109">**L'analisi e la gestione dei dispositivi di rete sono attualmente in anteprima pubblica**</span><span class="sxs-lookup"><span data-stu-id="c1d0f-109">**Scanning and managing network devices is currently in public preview**</span></span><br>
> <span data-ttu-id="c1d0f-110">Questa versione di anteprima viene fornita senza un contratto di servizio e non è consigliata per i carichi di lavoro di produzione.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-110">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="c1d0f-111">Alcune funzionalità potrebbero non essere supportate o avere funzionalità vincolate.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-111">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="c1d0f-112">Per altre informazioni, vedi [Funzionalità di anteprima di Microsoft Defender per Endpoint.](preview.md)</span><span class="sxs-lookup"><span data-stu-id="c1d0f-112">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

><span data-ttu-id="c1d0f-113">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c1d0f-113">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c1d0f-114">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

> [!NOTE]  
> <span data-ttu-id="c1d0f-115">Il Blog [sulle](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) valutazioni dell'individuazione e della vulnerabilità dei dispositivi di rete pubblicato \( 04-13-2021 fornisce informazioni dettagliate sulle nuove funzionalità di individuazione dei dispositivi di rete \) in Defender for Endpoint. </span><span class="sxs-lookup"><span data-stu-id="c1d0f-115">The [Network device discovery and vulnerability assessments](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) Blog \(published 04-13-2021\) provides insights into the new **Network device discovery** capabilities in Defender for Endpoint.</span></span> <span data-ttu-id="c1d0f-116">Questo articolo fornisce una panoramica  della sfida progettata per l'individuazione dei dispositivi di rete e informazioni dettagliate su come iniziare a usare queste nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-116">This article provides an overview of the challenge that **Network device discovery** is designed to address, and detailed information about how get started using these new capabilities.</span></span>

<span data-ttu-id="c1d0f-117">Le funzionalità di individuazione della rete sono disponibili nella sezione **Inventario** dispositivi del centro sicurezza Microsoft 365 e Microsoft Defender Security Center console.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-117">Network discovery capabilities are available in the **Device inventory** section of the Microsoft 365 security center and Microsoft Defender Security Center consoles.</span></span>  

<span data-ttu-id="c1d0f-118">Un dispositivo Microsoft Defender for Endpoint designato verrà usato in ogni segmento di rete per eseguire analisi periodiche autenticate di dispositivi di rete preconfigurati.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-118">A designated Microsoft Defender for Endpoint device will be used on each network segment to perform periodic authenticated scans of preconfigured network devices.</span></span> <span data-ttu-id="c1d0f-119">Una volta individuate, le funzionalità gestione di minacce e vulnerabilità di Defender for Endpoint forniscono flussi di lavoro integrati per proteggere commutatori, router, controller WLAN, firewall e gateway VPN individuati.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-119">Once discovered, Defender for Endpoint’s threat and vulnerability management capabilities provide integrated workflows to secure discovered switches, routers, WLAN controllers, firewalls, and VPN gateways.</span></span>  

<span data-ttu-id="c1d0f-120">Una volta individuati e classificati i dispositivi di rete, gli amministratori della sicurezza saranno in grado di ricevere i consigli più recenti sulla sicurezza ed esaminare le vulnerabilità individuate di recente nei dispositivi di rete distribuiti nelle organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-120">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>

## <a name="approach"></a><span data-ttu-id="c1d0f-121">Approccio</span><span class="sxs-lookup"><span data-stu-id="c1d0f-121">Approach</span></span>

<span data-ttu-id="c1d0f-122">I dispositivi di rete non vengono gestiti come endpoint standard poiché Defender for Endpoint non dispone di un sensore incorporato nei dispositivi di rete stessi.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-122">Network devices are not managed as standard endpoints since Defender for Endpoint doesn’t have a sensor built into the network devices themselves.</span></span> <span data-ttu-id="c1d0f-123">Questi tipi di dispositivi richiedono un approccio senza agenti in cui un'analisi remota oquisterà le informazioni necessarie dai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-123">These types of devices require an agentless approach where a remote scan will obtain the necessary information from the devices.</span></span> <span data-ttu-id="c1d0f-124">A seconda della topologia e delle caratteristiche di rete, un singolo dispositivo o alcuni dispositivi onboarded in Microsoft Defender for Endpoint eseguiranno analisi autenticate dei dispositivi di rete utilizzando SNMP (sola lettura).</span><span class="sxs-lookup"><span data-stu-id="c1d0f-124">Depending on the network topology and characteristics, a single device or a few devices onboarded to Microsoft Defender for Endpoint will perform authenticated scans of network devices using SNMP (read-only).</span></span>

<span data-ttu-id="c1d0f-125">Ci saranno due tipi di dispositivi da tenere presenti:</span><span class="sxs-lookup"><span data-stu-id="c1d0f-125">There will be two types of devices to keep in mind:</span></span>

- <span data-ttu-id="c1d0f-126">**Dispositivo di valutazione:** un dispositivo già onboarded che userai per analizzare i dispositivi di rete.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-126">**Assessment device**: A device that's already onboarded that you'll use to scan the network devices.</span></span>
- <span data-ttu-id="c1d0f-127">**Dispositivi di rete:** i dispositivi di rete che si prevede di analizzare e eseguire l'onboard.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-127">**Network devices**: The network devices you plan to scan and onboard.</span></span>

### <a name="vulnerability-management-for-network-devices"></a><span data-ttu-id="c1d0f-128">Gestione delle vulnerabilità per i dispositivi di rete</span><span class="sxs-lookup"><span data-stu-id="c1d0f-128">Vulnerability management for network devices</span></span> 

<span data-ttu-id="c1d0f-129">Una volta individuati e classificati i dispositivi di rete, gli amministratori della sicurezza saranno in grado di ricevere i consigli più recenti sulla sicurezza ed esaminare le vulnerabilità individuate di recente nei dispositivi di rete distribuiti nelle organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-129">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>  

## <a name="operating-systems-that-are-supported"></a><span data-ttu-id="c1d0f-130">Sistemi operativi supportati</span><span class="sxs-lookup"><span data-stu-id="c1d0f-130">Operating systems that are supported</span></span>

<span data-ttu-id="c1d0f-131">Attualmente sono supportati i seguenti sistemi operativi:</span><span class="sxs-lookup"><span data-stu-id="c1d0f-131">The following operating systems are currently supported:</span></span>

- <span data-ttu-id="c1d0f-132">Cisco IOS, IOS-XE, NX-OS</span><span class="sxs-lookup"><span data-stu-id="c1d0f-132">Cisco IOS, IOS-XE, NX-OS</span></span>
- <span data-ttu-id="c1d0f-133">Juniper JUNOS</span><span class="sxs-lookup"><span data-stu-id="c1d0f-133">Juniper JUNOS</span></span>
- <span data-ttu-id="c1d0f-134">HPE ArubaOS, software di commutazione di procura</span><span class="sxs-lookup"><span data-stu-id="c1d0f-134">HPE ArubaOS, Procurve Switch Software</span></span>
- <span data-ttu-id="c1d0f-135">Palo Alto Networks PAN-OS</span><span class="sxs-lookup"><span data-stu-id="c1d0f-135">Palo Alto Networks PAN-OS</span></span>

<span data-ttu-id="c1d0f-136">Nel tempo verranno aggiunti altri fornitori di rete e sistema operativo, in base ai dati raccolti dall'utilizzo dei clienti.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-136">More networking vendors and OS will be added over time, based on data gathered from customer usage.</span></span> <span data-ttu-id="c1d0f-137">Pertanto, si consiglia di configurare tutti i dispositivi di rete, anche se non sono specificati in questo elenco.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-137">Therefore, you are encouraged to configure all your network devices, even if they’re not specified in this list.</span></span>

## <a name="how-to-get-started"></a><span data-ttu-id="c1d0f-138">Come iniziare</span><span class="sxs-lookup"><span data-stu-id="c1d0f-138">How to get started</span></span>

<span data-ttu-id="c1d0f-139">Il primo passaggio consiste nel selezionare un dispositivo che eseguirà le analisi di rete autenticate.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-139">Your first step is to select a device that will perform the authenticated network scans.</span></span>

1. <span data-ttu-id="c1d0f-140">Decidi un dispositivo defender per endpoint onboarded (client o server) che dispone di una connessione di rete alla porta di gestione per i dispositivi di rete che vuoi analizzare.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-140">Decide on a Defender for Endpoint onboarded device (client or server) that has a network connection to the management port for the network devices you plan on scanning.</span></span> 

2. <span data-ttu-id="c1d0f-141">Il traffico SNMP tra il dispositivo di valutazione Defender for Endpoint e i dispositivi di rete di destinazione deve essere consentito (ad esempio, dal firewall).</span><span class="sxs-lookup"><span data-stu-id="c1d0f-141">SNMP traffic between the Defender for Endpoint assessment device and the targeted network devices must be allowed (for example, by the Firewall).</span></span>

3. <span data-ttu-id="c1d0f-142">Decidi quali dispositivi di rete verranno valutati per le vulnerabilità (ad esempio, un commutatore Cisco o un firewall Palo Alto Networks).</span><span class="sxs-lookup"><span data-stu-id="c1d0f-142">Decide which network devices will be assessed for vulnerabilities (for example: a Cisco switch or a Palo Alto Networks firewall).</span></span>  

4. <span data-ttu-id="c1d0f-143">Assicurati che la sola lettura SNMP sia abilitata in tutti i dispositivi di rete configurati per consentire al dispositivo di valutazione Defender for Endpoint di eseguire query sui dispositivi di rete configurati.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-143">Make sure SNMP read-only is enabled on all configured network devices to allow the Defender for Endpoint assessment device to query the configured network devices.</span></span> <span data-ttu-id="c1d0f-144">La scrittura SNMP non è necessaria per le funzionalità appropriate di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-144">‘SNMP write’ isn't needed for the proper functionality of this feature.</span></span>

5. <span data-ttu-id="c1d0f-145">Ottenere gli indirizzi IP dei dispositivi di rete da analizzare (o le subnet in cui questi dispositivi vengono distribuiti).</span><span class="sxs-lookup"><span data-stu-id="c1d0f-145">Obtain the IP addresses of the network devices to be scanned (or the subnets where these devices are deployed).</span></span>

6. <span data-ttu-id="c1d0f-146">Ottenere le credenziali SNMP dei dispositivi di rete (ad esempio: Community String, noAuthNoPriv, authNoPriv, authPriv).</span><span class="sxs-lookup"><span data-stu-id="c1d0f-146">Obtain the SNMP credentials of the network devices (for example: Community String, noAuthNoPriv, authNoPriv, authPriv).</span></span> <span data-ttu-id="c1d0f-147">Sarà necessario fornire le credenziali durante la configurazione di un nuovo processo di valutazione.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-147">You’ll be required to provide the credentials when configuring a new assessment job.</span></span>  

7. <span data-ttu-id="c1d0f-148">Configurazione del client proxy: non è necessaria alcuna configurazione aggiuntiva oltre ai requisiti di Defender per il proxy del dispositivo endpoint.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-148">Proxy client configuration: No extra configuration is required other than the Defender for Endpoint device proxy requirements.</span></span>

8. <span data-ttu-id="c1d0f-149">Per consentire l'autenticazione e il corretto funzionamento dello scanner di rete, è essenziale aggiungere i domini/URL seguenti:</span><span class="sxs-lookup"><span data-stu-id="c1d0f-149">To allow the network scanner to be authenticated and work properly, it's essential that you add the following domains/URLs:</span></span>

    - <span data-ttu-id="c1d0f-150">login.windows.net</span><span class="sxs-lookup"><span data-stu-id="c1d0f-150">login.windows.net</span></span>  
    - <span data-ttu-id="c1d0f-151">\*.securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="c1d0f-151">\*.securitycenter.windows.com</span></span>
    - <span data-ttu-id="c1d0f-152">login.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c1d0f-152">login.microsoftonline.com</span></span>
    - <span data-ttu-id="c1d0f-153">\*.blob.core.windows.net/networkscannerstable/ \*</span><span class="sxs-lookup"><span data-stu-id="c1d0f-153">\*.blob.core.windows.net/networkscannerstable/ \*</span></span>

    > [!NOTE]
    > <span data-ttu-id="c1d0f-154">Non tutti gli URL sono specificati nell'elenco documentato di Defender for Endpoint della raccolta dati consentita.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-154">Not all URLs are specified in the Defender for Endpoint documented list of allowed data collection.</span></span>

## <a name="permissions"></a><span data-ttu-id="c1d0f-155">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c1d0f-155">Permissions</span></span>

<span data-ttu-id="c1d0f-156">Per configurare i processi di valutazione, è necessaria l'opzione di autorizzazione utente seguente: **Gestire le impostazioni di sicurezza nel Centro sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="c1d0f-156">To configure assessment jobs, the following user permission option is required: **Manage security settings in Security Center**.</span></span> <span data-ttu-id="c1d0f-157">Per trovare l'autorizzazione, andare a **Impostazioni**  >  **ruoli**.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-157">You can find the permission by going to **Settings** > **Roles**.</span></span> <span data-ttu-id="c1d0f-158">Per ulteriori informazioni, vedere [Create and manage roles for role-based access control](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c1d0f-158">For more information, see [Create and manage roles for role-based access control](user-roles.md).</span></span>

## <a name="install-the-network-scanner"></a><span data-ttu-id="c1d0f-159">Installare lo scanner di rete</span><span class="sxs-lookup"><span data-stu-id="c1d0f-159">Install the network scanner</span></span>

1. <span data-ttu-id="c1d0f-160">Vai a **Microsoft 365 sicurezza Impostazioni** processi di valutazione degli  >    >  **endpoint**  >   (in Valutazioni **di rete**).</span><span class="sxs-lookup"><span data-stu-id="c1d0f-160">Go to **Microsoft 365 security** > **Settings** > **Endpoints** > **Assessment jobs** (under **Network assessments**).</span></span>
    1. <span data-ttu-id="c1d0f-161">Nel Microsoft Defender Security Center, passare alla pagina Impostazioni > processi di valutazione.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-161">In the Microsoft Defender Security Center, go to Settings > Assessment jobs page.</span></span>

2. <span data-ttu-id="c1d0f-162">Scarica lo scanner di rete e installalo nel dispositivo di valutazione Defender for Endpoint designato.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-162">Download the network scanner and install it on the designated Defender for Endpoint assessment device.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c1d0f-163">![Pulsante Scarica scanner](images/assessment-jobs-download-scanner.png)</span><span class="sxs-lookup"><span data-stu-id="c1d0f-163">![Download scanner button](images/assessment-jobs-download-scanner.png)</span></span>

## <a name="network-scanner-installation--registration"></a><span data-ttu-id="c1d0f-164">Installazione scanner di rete & registrazione</span><span class="sxs-lookup"><span data-stu-id="c1d0f-164">Network scanner installation & registration</span></span>

<span data-ttu-id="c1d0f-165">Il processo di accesso può essere completato sul dispositivo di valutazione designato stesso o su qualsiasi altro dispositivo (ad esempio, il dispositivo client personale).</span><span class="sxs-lookup"><span data-stu-id="c1d0f-165">The signing-in process can be completed on the designated assessment device itself or any other device (for example, your personal client device).</span></span>

<span data-ttu-id="c1d0f-166">Per completare il processo di registrazione dello scanner di rete:</span><span class="sxs-lookup"><span data-stu-id="c1d0f-166">To complete the network scanner registration process:</span></span>

1. <span data-ttu-id="c1d0f-167">Copiare e seguire l'URL visualizzato nella riga di comando e utilizzare il codice di installazione fornito per completare il processo di registrazione.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-167">Copy and follow the URL that appears on the command line and use the provided installation code to complete the registration process.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c1d0f-168">Potrebbe essere necessario modificare le impostazioni del prompt dei comandi per poter copiare l'URL.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-168">You may need to change Command Prompt settings to be able to copy the URL.</span></span>

2. <span data-ttu-id="c1d0f-169">Immetti il codice e accedi con un account Microsoft con l'autorizzazione Defender for Endpoint denominata "Gestire le impostazioni di sicurezza nel Centro sicurezza".</span><span class="sxs-lookup"><span data-stu-id="c1d0f-169">Enter the code and sign in using a Microsoft account that has the Defender for Endpoint permission called "Manage security settings in Security Center."</span></span>

3. <span data-ttu-id="c1d0f-170">Al termine, verrà visualizzato un messaggio di conferma dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-170">When finished, you should see a message confirming you have signed in.</span></span>

## <a name="configure-a-new-assessment-job"></a><span data-ttu-id="c1d0f-171">Configurare un nuovo processo di valutazione</span><span class="sxs-lookup"><span data-stu-id="c1d0f-171">Configure a new assessment job</span></span>  

<span data-ttu-id="c1d0f-172">Nella pagina Processi di valutazione in **Impostazioni** selezionare **Aggiungi processo di valutazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-172">In the Assessment jobs page in **Settings**, select **Add network assessment job**.</span></span> <span data-ttu-id="c1d0f-173">Segui il processo di configurazione per scegliere i dispositivi di rete da analizzare regolarmente e aggiungere all'inventario dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-173">Follow the set-up process to choose network devices to be scanned regularly and added to the device inventory.</span></span>

<span data-ttu-id="c1d0f-174">Per impedire la duplicazione dei dispositivi nell'inventario dei dispositivi di rete, assicurati che ogni indirizzo IP sia configurato una sola volta tra più dispositivi di valutazione.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-174">To prevent device duplication in the network device inventory, make sure each IP address is configured only once across multiple assessment devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c1d0f-175">![Pulsante Aggiungi processo di valutazione di rete](images/assessment-jobs-add.png)</span><span class="sxs-lookup"><span data-stu-id="c1d0f-175">![Add network assessment job button](images/assessment-jobs-add.png)</span></span>

<span data-ttu-id="c1d0f-176">Aggiunta dei passaggi di un processo di valutazione della rete:</span><span class="sxs-lookup"><span data-stu-id="c1d0f-176">Adding a network assessment job steps:</span></span>

1. <span data-ttu-id="c1d0f-177">Scegliere il nome di un processo di valutazione e il "dispositivo di valutazione" in cui è stato installato lo scanner di rete.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-177">Choose an ‘Assessment job’ name and the ‘Assessment device’ on which the network scanner was installed.</span></span> <span data-ttu-id="c1d0f-178">Questo dispositivo eseguirà le analisi periodiche autenticate.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-178">This device will perform the periodic authenticated scans.</span></span>

2. <span data-ttu-id="c1d0f-179">Aggiungere gli indirizzi IP dei dispositivi di rete di destinazione da analizzare (o le subnet in cui questi dispositivi vengono distribuiti).</span><span class="sxs-lookup"><span data-stu-id="c1d0f-179">Add IP addresses of target network devices to be scanned (or the subnets where these devices are deployed).</span></span> 

3. <span data-ttu-id="c1d0f-180">Aggiungere le credenziali SNMP necessarie dei dispositivi di rete di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-180">Add required SNMP credentials of the target network devices.</span></span> 

4. <span data-ttu-id="c1d0f-181">Salvare il processo di valutazione della rete appena configurato per avviare l'analisi periodica della rete.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-181">Save the newly configured network assessment job to start the periodic network scan.</span></span> 

### <a name="scan-and-add-network-devices"></a><span data-ttu-id="c1d0f-182">Analizzare e aggiungere dispositivi di rete</span><span class="sxs-lookup"><span data-stu-id="c1d0f-182">Scan and add network devices</span></span>

<span data-ttu-id="c1d0f-183">Durante il processo di configurazione, è possibile eseguire un'analisi di test una sola volta per verificare che:</span><span class="sxs-lookup"><span data-stu-id="c1d0f-183">During the set-up process, you can perform a one time test scan to verify that:</span></span>

- <span data-ttu-id="c1d0f-184">Esiste una connettività tra il dispositivo di valutazione Defender for Endpoint e i dispositivi di rete di destinazione configurati.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-184">There is connectivity between the Defender for Endpoint assessment device and the configured target network devices.</span></span>
- <span data-ttu-id="c1d0f-185">Le credenziali SNMP configurate sono corrette.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-185">The configured SNMP credentials are correct.</span></span>

<span data-ttu-id="c1d0f-186">Ogni dispositivo di valutazione può supportare fino a 1.500 analisi degli indirizzi IP riusciti.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-186">Each assessment device can support up to 1,500 successful IP addresses scan.</span></span> <span data-ttu-id="c1d0f-187">Ad esempio, se si analizzano 10 subnet diverse in cui solo 100 indirizzi IP restituiscono risultati positivi, sarà possibile analizzare 1.400 indirizzi IP aggiuntivi da altre subnet sullo stesso dispositivo di valutazione.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-187">For example, if you scan 10 different subnets where only 100 IP addresses return successful results, you will be able to scan 1,400 IP additional addresses from other subnets on the same assessment device.</span></span>  

<span data-ttu-id="c1d0f-188">Se sono presenti più intervalli di indirizzi IP/subnet da analizzare, la visualizzazione dei risultati dell'analisi di test avrà alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-188">If there are multiple IP address ranges/subnets to scan, the test scan results will take several minutes to show up.</span></span> <span data-ttu-id="c1d0f-189">Sarà disponibile un'analisi di test per un massimo di 1.024 indirizzi.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-189">A test scan will be available for up to 1,024 addresses.</span></span>

<span data-ttu-id="c1d0f-190">Una volta visualizzati i risultati, puoi scegliere quali dispositivi verranno inclusi nell'analisi periodica.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-190">Once the results show up, you can choose which devices will be included in the periodic scan.</span></span> <span data-ttu-id="c1d0f-191">Se si ignora la visualizzazione dei risultati dell'analisi, tutti gli indirizzi IP configurati verranno aggiunti al processo di valutazione della rete (indipendentemente dalla risposta del dispositivo).</span><span class="sxs-lookup"><span data-stu-id="c1d0f-191">If you skip viewing the scan results, all configured IP addresses will be added to the network assessment job (regardless of the device’s response).</span></span> <span data-ttu-id="c1d0f-192">È inoltre possibile esportare i risultati dell'analisi.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-192">The scan results can also be exported.</span></span>

## <a name="device-inventory"></a><span data-ttu-id="c1d0f-193">Inventario dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="c1d0f-193">Device inventory</span></span>

<span data-ttu-id="c1d0f-194">I nuovi dispositivi individuati verranno visualizzati nella nuova **scheda Dispositivi di** rete nella pagina **Inventario** dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-194">Newly discovered devices will be shown under the new **Network devices** tab in the **Device inventory** page.</span></span> <span data-ttu-id="c1d0f-195">L'aggiunta di un processo di valutazione può richiedere fino a due ore prima dell'aggiornamento dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-195">It may take up to two hours after adding an assessment job until the devices are updated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c1d0f-196">![Sezione Dispositivi di rete nell'inventario dei dispositivi](images/assessment-jobs-device-inventory.png)</span><span class="sxs-lookup"><span data-stu-id="c1d0f-196">![Network devices section in the Device inventory](images/assessment-jobs-device-inventory.png)</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c1d0f-197">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="c1d0f-197">Troubleshooting</span></span>

### <a name="network-scanner-installation-has-failed"></a><span data-ttu-id="c1d0f-198">Installazione scanner di rete non riuscita</span><span class="sxs-lookup"><span data-stu-id="c1d0f-198">Network scanner installation has failed</span></span>

<span data-ttu-id="c1d0f-199">Verificare che gli URL necessari siano aggiunti ai domini consentiti nelle impostazioni del firewall.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-199">Verify that the required URLs are added to the allowed domains in your firewall settings.</span></span> <span data-ttu-id="c1d0f-200">Verificare inoltre che le impostazioni proxy siano configurate come descritto in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span><span class="sxs-lookup"><span data-stu-id="c1d0f-200">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a><span data-ttu-id="c1d0f-201">La Microsoft.com/devicelogin web non è stata visualizzata</span><span class="sxs-lookup"><span data-stu-id="c1d0f-201">The Microsoft.com/devicelogin web page did not show up</span></span>

<span data-ttu-id="c1d0f-202">Verificare che gli URL necessari siano aggiunti ai domini consentiti nel firewall.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-202">Verify that the required URLs are added to the allowed domains in your firewall.</span></span> <span data-ttu-id="c1d0f-203">Verificare inoltre che le impostazioni proxy siano configurate come descritto in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span><span class="sxs-lookup"><span data-stu-id="c1d0f-203">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a><span data-ttu-id="c1d0f-204">I dispositivi di rete non vengono visualizzati nell'inventario dei dispositivi dopo diverse ore</span><span class="sxs-lookup"><span data-stu-id="c1d0f-204">Network devices are not shown in the device inventory after several hours</span></span>

<span data-ttu-id="c1d0f-205">I risultati dell'analisi devono essere aggiornati alcune ore dopo l'analisi iniziale eseguita dopo il completamento della configurazione del processo di valutazione.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-205">The scan results should be updated a few hours after the initial scan that took place after completing the assessment job configuration.</span></span>

<span data-ttu-id="c1d0f-206">Se i dispositivi non sono ancora visualizzati, verificare che il servizio 'MdatpNetworkScanService' sia in esecuzione nei dispositivi di valutazione, in cui è stato installato lo scanner di rete, ed eseguire un'analisi "Esegui" nella configurazione del processo di valutazione pertinente.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-206">If devices are still not shown, verify that the service ‘MdatpNetworkScanService’ is running on your assessment devices, on which you installed the network scanner, and perform a “Run scan” in the relevant assessment job configuration.</span></span>  

<span data-ttu-id="c1d0f-207">Se non si ottengono ancora risultati dopo 5 minuti, riavviare il servizio.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-207">If you still don’t get results after 5 minutes, restart the service.</span></span>  

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a><span data-ttu-id="c1d0f-208">L'ora dell'ultima volta per i dispositivi è più lunga di 24 ore</span><span class="sxs-lookup"><span data-stu-id="c1d0f-208">Devices last seen time is longer than 24 hours</span></span>

<span data-ttu-id="c1d0f-209">Verificare che lo scanner sia in esecuzione correttamente.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-209">Validate that the scanner is running properly.</span></span> <span data-ttu-id="c1d0f-210">Passare quindi alla definizione di analisi e selezionare "Esegui test".</span><span class="sxs-lookup"><span data-stu-id="c1d0f-210">Then go to the scan definition and select “Run test.”</span></span> <span data-ttu-id="c1d0f-211">Controllare quali messaggi di errore vengono restituiti dagli indirizzi IP pertinenti.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-211">Check what error messages are returning from the relevant IP addresses.</span></span>

### <a name="required-threat-and-vulnerability-management-user-permission"></a><span data-ttu-id="c1d0f-212">Autorizzazione gestione di minacce e vulnerabilità'utente</span><span class="sxs-lookup"><span data-stu-id="c1d0f-212">Required threat and vulnerability management user permission</span></span>

<span data-ttu-id="c1d0f-213">Registrazione completata con un errore: "Sembra che non si disponga di autorizzazioni sufficienti per l'aggiunta di un nuovo agente.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-213">Registration finished with an error: "It looks like you don't have sufficient permissions for adding a new agent.</span></span> <span data-ttu-id="c1d0f-214">L'autorizzazione necessaria è "Gestire le impostazioni di sicurezza nel Centro sicurezza".</span><span class="sxs-lookup"><span data-stu-id="c1d0f-214">The required permission is 'Manage security settings in Security Center'."</span></span>

<span data-ttu-id="c1d0f-215">Premere un tasto qualsiasi per uscire.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-215">Press any key to exit.</span></span>

<span data-ttu-id="c1d0f-216">Chiedere all'amministratore di sistema di assegnare le autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-216">Ask your system administrator to assign you the required permissions.</span></span> <span data-ttu-id="c1d0f-217">In alternativa, chiedere a un altro membro rilevante di aiutarti con il processo di accesso fornendo loro il codice di accesso e il collegamento.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-217">Alternately, ask another relevant member to help you with the sign-in process by providing them with the sign-in code and link.</span></span>

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a><span data-ttu-id="c1d0f-218">Il processo di registrazione non riesce utilizzando il collegamento fornito nella riga di comando nel processo di registrazione</span><span class="sxs-lookup"><span data-stu-id="c1d0f-218">Registration process fails using provided link in the command line in registration process</span></span>

<span data-ttu-id="c1d0f-219">Prova un browser diverso o copia il collegamento e il codice di accesso in un altro dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-219">Try a different browser or copy the sign-in link and code to a different device.</span></span>

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a><span data-ttu-id="c1d0f-220">Testo troppo piccolo o non in grado di copiare testo dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="c1d0f-220">Text too small or can’t copy text from command line</span></span>

<span data-ttu-id="c1d0f-221">Modifica le impostazioni della riga di comando nel dispositivo per consentire la copia e la modifica delle dimensioni del testo.</span><span class="sxs-lookup"><span data-stu-id="c1d0f-221">Change command-line settings on your device to allow copying and change text size.</span></span>

## <a name="related-articles"></a><span data-ttu-id="c1d0f-222">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="c1d0f-222">Related articles</span></span>

- [<span data-ttu-id="c1d0f-223">Inventario dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="c1d0f-223">Device inventory</span></span>](machines-view-overview.md)
- [<span data-ttu-id="c1d0f-224">Configurare le funzionalità avanzate</span><span class="sxs-lookup"><span data-stu-id="c1d0f-224">Configure advanced features</span></span>](advanced-features.md)
