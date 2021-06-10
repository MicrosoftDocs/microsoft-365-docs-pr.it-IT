---
title: Configurare Microsoft Defender per la distribuzione degli endpoint
description: Informazioni su come configurare la distribuzione per Microsoft Defender for Endpoint
keywords: distribuire, configurare, convalida delle licenze, configurazione tenant, configurazione di rete
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
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b49565c45c1f38d0d2ce71b097af079782ba4de
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636195"
---
# <a name="set-up-microsoft-defender-for-endpoint-deployment"></a><span data-ttu-id="0647e-104">Configurare Microsoft Defender per la distribuzione degli endpoint</span><span class="sxs-lookup"><span data-stu-id="0647e-104">Set up Microsoft Defender for Endpoint deployment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0647e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0647e-105">**Applies to:**</span></span>
- [<span data-ttu-id="0647e-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="0647e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0647e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0647e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0647e-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="0647e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0647e-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="0647e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="0647e-110">La distribuzione di Defender per Endpoint è un processo in tre fasi:</span><span class="sxs-lookup"><span data-stu-id="0647e-110">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="0647e-111">[![fase di distribuzione - preparazione](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="0647e-111">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="0647e-112">Fase 1: preparazione</span><span class="sxs-lookup"><span data-stu-id="0647e-112">Phase 1: Prepare</span></span>](prepare-deployment.md) | ![fase di distribuzione - installazione](images/phase-diagrams/setup.png)<br><span data-ttu-id="0647e-114">Fase 2: configurazione</span><span class="sxs-lookup"><span data-stu-id="0647e-114">Phase 2: Setup</span></span> | <span data-ttu-id="0647e-115">[![fase di distribuzione - onboard](images/phase-diagrams/onboard.png)](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="0647e-115">[![deployment phase - onboard](images/phase-diagrams/onboard.png)](onboarding.md)</span></span><br>[<span data-ttu-id="0647e-116">Fase 3: onboarding</span><span class="sxs-lookup"><span data-stu-id="0647e-116">Phase 3: Onboard</span></span>](onboarding.md) |
| ----- | ----- | ----- |
| | <span data-ttu-id="0647e-117">*Sei qui!*</span><span class="sxs-lookup"><span data-stu-id="0647e-117">*You are here!*</span></span>||

<span data-ttu-id="0647e-118">Si è attualmente in fase di configurazione.</span><span class="sxs-lookup"><span data-stu-id="0647e-118">You are currently in the set-up phase.</span></span>

<span data-ttu-id="0647e-119">In questo scenario di distribuzione verrà illustrata la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="0647e-119">In this deployment scenario, you'll be guided through the steps on:</span></span>
- <span data-ttu-id="0647e-120">Convalida delle licenze</span><span class="sxs-lookup"><span data-stu-id="0647e-120">Licensing validation</span></span>
- <span data-ttu-id="0647e-121">Configurazione tenant</span><span class="sxs-lookup"><span data-stu-id="0647e-121">Tenant configuration</span></span>
- <span data-ttu-id="0647e-122">Configurazione di rete</span><span class="sxs-lookup"><span data-stu-id="0647e-122">Network configuration</span></span>


>[!NOTE]
><span data-ttu-id="0647e-123">Allo scopo di guidare l'utente attraverso una distribuzione tipica, questo scenario copre solo l'uso di Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="0647e-123">For the purpose of guiding you through a typical deployment, this scenario will only cover the use of Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="0647e-124">Defender for Endpoint supporta l'uso di altri strumenti di onboarding, ma non copre questi scenari nella guida alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0647e-124">Defender for Endpoint supports the use of other onboarding tools but won't cover those scenarios in the deployment guide.</span></span> <span data-ttu-id="0647e-125">Per altre informazioni, vedi [Onboard di dispositivi a Microsoft Defender per Endpoint.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="0647e-125">For more information, see [Onboard devices to Microsoft Defender for Endpoint](onboard-configure.md).</span></span>

## <a name="check-license-state"></a><span data-ttu-id="0647e-126">Controllare lo stato della licenza</span><span class="sxs-lookup"><span data-stu-id="0647e-126">Check license state</span></span>

<span data-ttu-id="0647e-127">Il controllo dello stato della licenza e del provisioning corretto può essere eseguito tramite l'interfaccia di amministrazione o tramite il **portale Microsoft Azure .**</span><span class="sxs-lookup"><span data-stu-id="0647e-127">Checking for the license state and whether it got properly provisioned, can be done through the admin center or through the **Microsoft Azure portal**.</span></span>

1. <span data-ttu-id="0647e-128">Per visualizzare le licenze, passare al **portale di Microsoft Azure** e passare alla Microsoft Azure licenza del [portale.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)</span><span class="sxs-lookup"><span data-stu-id="0647e-128">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Immagine della pagina Licenze di Azure](images/atp-licensing-azure-portal.png)

1. <span data-ttu-id="0647e-130">In alternativa, nell'interfaccia di amministrazione passare a **Fatturazione**  >  **Abbonamenti.**</span><span class="sxs-lookup"><span data-stu-id="0647e-130">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="0647e-131">Sullo schermo verranno visualizzate tutte le licenze di cui è stato eseguito il provisioning e il relativo **stato corrente.**</span><span class="sxs-lookup"><span data-stu-id="0647e-131">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![Immagine delle licenze di fatturazione](images/atp-billing-subscriptions.png)


## <a name="cloud-service-provider-validation"></a><span data-ttu-id="0647e-133">Convalida del provider di servizi cloud</span><span class="sxs-lookup"><span data-stu-id="0647e-133">Cloud Service Provider validation</span></span>

<span data-ttu-id="0647e-134">Per ottenere l'accesso alle licenze di cui viene eseguito il provisioning per l'azienda e per controllare lo stato delle licenze, passare all'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="0647e-134">To gain access into which licenses are provisioned to your company, and to check the state of the licenses, go to the admin center.</span></span>

1. <span data-ttu-id="0647e-135">Nel **portale per i partner** selezionare **Amministra servizi > Office 365**.</span><span class="sxs-lookup"><span data-stu-id="0647e-135">From the **Partner portal**, select **Administer services > Office 365**.</span></span>

2. <span data-ttu-id="0647e-136">Facendo clic sul **collegamento Portale per i** partner verrà aperta l'opzione Amministratore per conto **di** e si avrà accesso all'interfaccia di amministrazione del cliente.</span><span class="sxs-lookup"><span data-stu-id="0647e-136">Clicking on the **Partner portal** link will open the **Admin on behalf** option and will give you access to the customer admin center.</span></span>

   ![Immagine del portale di amministrazione di O365](images/atp-O365-admin-portal-customer.png)



## <a name="tenant-configuration"></a><span data-ttu-id="0647e-138">Configurazione tenant</span><span class="sxs-lookup"><span data-stu-id="0647e-138">Tenant Configuration</span></span>
<span data-ttu-id="0647e-139">L'onboarding in Microsoft Defender per Endpoint è facile.</span><span class="sxs-lookup"><span data-stu-id="0647e-139">Onboarding to Microsoft Defender for Endpoint is easy.</span></span> <span data-ttu-id="0647e-140">Dal menu di spostamento seleziona qualsiasi elemento nella sezione Endpoint o qualsiasi funzionalità di Microsoft 365 Defender, ad esempio Eventi imprevisti, Ricerca, Centro notifiche o Analisi delle minacce per avviare il processo di onboarding.</span><span class="sxs-lookup"><span data-stu-id="0647e-140">From the navigation menu, select any item under the Endpoints section, or any Microsoft 365 Defender feature such as Incidents, Hunting, Action center, or Threat analytics to initiate the onboarding process.</span></span>

<span data-ttu-id="0647e-141">Da un Web browser passare al Centro [sicurezza Microsoft 365 sicurezza](https://security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="0647e-141">From a web browser, navigate to the [Microsoft 365 Security Center](https://security.microsoft.com).</span></span>

## <a name="network-configuration"></a><span data-ttu-id="0647e-142">Configurazione di rete</span><span class="sxs-lookup"><span data-stu-id="0647e-142">Network configuration</span></span>
<span data-ttu-id="0647e-143">Se l'organizzazione non richiede agli endpoint di utilizzare un proxy per accedere a Internet, ignorare questa sezione.</span><span class="sxs-lookup"><span data-stu-id="0647e-143">If the organization doesn't require the endpoints to use a Proxy to access the Internet, skip this section.</span></span>

<span data-ttu-id="0647e-144">Il sensore Microsoft Defender per endpoint richiede che Microsoft Windows HTTP (WinHTTP) segnali dati dei sensori e comunichi con il servizio Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="0647e-144">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="0647e-145">Il sensore incorporato di Microsoft Defender for Endpoint viene eseguito nel contesto di sistema usando l'account LocalSystem.</span><span class="sxs-lookup"><span data-stu-id="0647e-145">The embedded Microsoft Defender for Endpoint sensor runs in the system context using the LocalSystem account.</span></span> <span data-ttu-id="0647e-146">Il sensore usa i servizi HTTP di Microsoft Windows (WinHTTP) per abilitare le comunicazioni con il servizio cloud Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="0647e-146">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Microsoft Defender for Endpoint cloud service.</span></span> <span data-ttu-id="0647e-147">L'impostazione di configurazione WinHTTP è indipendente dalle impostazioni del proxy di esplorazione Internet di Windows Internet (WinINet) e può individuare un server proxy solo utilizzando i metodi di individuazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="0647e-147">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

<span data-ttu-id="0647e-148">**Metodi di individuazione automatica:**</span><span class="sxs-lookup"><span data-stu-id="0647e-148">**Autodiscovery methods:**</span></span>

-   <span data-ttu-id="0647e-149">Proxy trasparente</span><span class="sxs-lookup"><span data-stu-id="0647e-149">Transparent proxy</span></span>

-   <span data-ttu-id="0647e-150">WPAD (Web Proxy Autodiscovery Protocol)</span><span class="sxs-lookup"><span data-stu-id="0647e-150">Web Proxy Autodiscovery Protocol (WPAD)</span></span>

<span data-ttu-id="0647e-151">Se nella topologia di rete è stato implementato un proxy Trasparente o WPAD, non è necessario disporre di impostazioni di configurazione speciali.</span><span class="sxs-lookup"><span data-stu-id="0647e-151">If a Transparent proxy or WPAD has been implemented in the network topology, there is no need for special configuration settings.</span></span> <span data-ttu-id="0647e-152">Per ulteriori informazioni sulle esclusioni di URL di Microsoft Defender for Endpoint nel proxy, vedere la sezione URL del servizio [proxy](production-deployment.md#proxy-service-urls) in questo documento per l'elenco url consentiti o in Configurare le impostazioni di connettività Internet e [proxy del dispositivo.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="0647e-152">For more information on Microsoft Defender for Endpoint URL exclusions in the proxy, see the [Proxy Service URLs](production-deployment.md#proxy-service-urls) section in this document for the URLs allow list or on [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="0647e-153">**Configurazione manuale del proxy statico:**</span><span class="sxs-lookup"><span data-stu-id="0647e-153">**Manual static proxy configuration:**</span></span>

-   <span data-ttu-id="0647e-154">Configurazione basata sul registro</span><span class="sxs-lookup"><span data-stu-id="0647e-154">Registry-based configuration</span></span>

-   <span data-ttu-id="0647e-155">WinHTTP configurato con il comando netsh</span><span class="sxs-lookup"><span data-stu-id="0647e-155">WinHTTP configured using netsh command</span></span> <br> <span data-ttu-id="0647e-156">Adatto solo per i desktop in una topologia stabile (ad esempio, un desktop in una rete aziendale dietro lo stesso proxy)</span><span class="sxs-lookup"><span data-stu-id="0647e-156">Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

### <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="0647e-157">Configurare manualmente il server proxy con un proxy statico basato sul registro</span><span class="sxs-lookup"><span data-stu-id="0647e-157">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="0647e-158">Configurare un proxy statico basato sul Registro di sistema per consentire solo al sensore Microsoft Defender for Endpoint di segnalare i dati di diagnostica e comunicare con Microsoft Defender per i servizi endpoint se un computer non è autorizzato a connettersi a Internet.</span><span class="sxs-lookup"><span data-stu-id="0647e-158">Configure a registry-based static proxy to allow only Microsoft Defender for Endpoint sensor to report diagnostic data and communicate with Microsoft Defender for Endpoint services if a computer isn't permitted to connect to the Internet.</span></span> <span data-ttu-id="0647e-159">Il proxy statico è configurabile tramite Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="0647e-159">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="0647e-160">I criteri di gruppo sono disponibili in:</span><span class="sxs-lookup"><span data-stu-id="0647e-160">The group policy can be found under:</span></span>

 - <span data-ttu-id="0647e-161">Modelli amministrativi Windows componenti di raccolta dati e build di anteprima Configurare l'utilizzo del proxy autenticato per il servizio Esperienza \> \> utente \> connessa e telemetria</span><span class="sxs-lookup"><span data-stu-id="0647e-161">Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service</span></span>
     - <span data-ttu-id="0647e-162">Impostarlo su **Abilitato e** selezionare Disabilita utilizzo **proxy autenticato**</span><span class="sxs-lookup"><span data-stu-id="0647e-162">Set it to **Enabled** and select **Disable Authenticated Proxy usage**</span></span>

1. <span data-ttu-id="0647e-163">Avviare la Console Gestione Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="0647e-163">Open the Group Policy Management Console.</span></span>
2. <span data-ttu-id="0647e-164">Creare un criterio o modificare un criterio esistente in base alle procedure dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0647e-164">Create a policy or edit an existing policy based off the organizational practices.</span></span>
3. <span data-ttu-id="0647e-165">Modificare i Criteri di gruppo e passare a Modelli amministrativi Windows componenti Raccolta dati e build di anteprima Configurare l'utilizzo del proxy autenticato per il servizio Esperienza utente **\> \> \> connessa** e telemetria .</span><span class="sxs-lookup"><span data-stu-id="0647e-165">Edit the Group Policy and navigate to **Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**.</span></span> 
    <span data-ttu-id="0647e-166">![Immagine della configurazione di Criteri di gruppo](images/atp-gpo-proxy1.png)</span><span class="sxs-lookup"><span data-stu-id="0647e-166">![Image of Group Policy configuration](images/atp-gpo-proxy1.png)</span></span>

4. <span data-ttu-id="0647e-167">Selezionare **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="0647e-167">Select **Enabled**.</span></span>
5. <span data-ttu-id="0647e-168">Selezionare **Disabilita utilizzo proxy autenticato**.</span><span class="sxs-lookup"><span data-stu-id="0647e-168">Select **Disable Authenticated Proxy usage**.</span></span>
   
6. <span data-ttu-id="0647e-169">Passare a Modelli amministrativi Windows componenti Raccolta dati e Build di anteprima **Configurare esperienze utente connesse e \> \> \> telemetria.**</span><span class="sxs-lookup"><span data-stu-id="0647e-169">Navigate to **Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure connected user experiences and telemetry**.</span></span>
    <span data-ttu-id="0647e-170">![Immagine dell'impostazione di configurazione di Criteri di gruppo](images/atp-gpo-proxy2.png)</span><span class="sxs-lookup"><span data-stu-id="0647e-170">![Image of Group Policy configuration setting](images/atp-gpo-proxy2.png)</span></span>
7. <span data-ttu-id="0647e-171">Selezionare **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="0647e-171">Select **Enabled**.</span></span>
8. <span data-ttu-id="0647e-172">Immettere il **nome del server proxy**.</span><span class="sxs-lookup"><span data-stu-id="0647e-172">Enter the **Proxy Server Name**.</span></span>

<span data-ttu-id="0647e-173">Il criterio imposta due valori di registro`TelemetryProxyServer` come REG_SZ e `DisableEnterpriseAuthProxy` REG_DWORD nella chiave di registro`HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span><span class="sxs-lookup"><span data-stu-id="0647e-173">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

<span data-ttu-id="0647e-174">Il valore del Registro `TelemetryProxyServer` di sistema assume il formato stringa seguente:</span><span class="sxs-lookup"><span data-stu-id="0647e-174">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

```text
<server name or ip>:<port>
```

<span data-ttu-id="0647e-175">Ad esempio: 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="0647e-175">For example: 10.0.0.6:8080</span></span>

<span data-ttu-id="0647e-176">Il valore del registro `DisableEnterpriseAuthProxy` deve essere impostato su 1.</span><span class="sxs-lookup"><span data-stu-id="0647e-176">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

###  <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="0647e-177">Configurare manualmente il server proxy utilizzando il comando netsh</span><span class="sxs-lookup"><span data-stu-id="0647e-177">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="0647e-178">Usare netsh per configurare un proxy statico a livello di sistema.</span><span class="sxs-lookup"><span data-stu-id="0647e-178">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> - <span data-ttu-id="0647e-179">Questa operazione avrà effetto su tutte le applicazioni, inclusi i servizi di Windows che usano WinHTTP con proxy predefinito.</span><span class="sxs-lookup"><span data-stu-id="0647e-179">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="0647e-180">I portatili che cambiano topologia (ad esempio, da ufficio a casa) non funzionano correttamente con netsh.</span><span class="sxs-lookup"><span data-stu-id="0647e-180">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="0647e-181">È consigliabile usare la configurazione del proxy statico basata sul registro.</span><span class="sxs-lookup"><span data-stu-id="0647e-181">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="0647e-182">Aprire un prompt dei comandi con privilegi elevati:</span><span class="sxs-lookup"><span data-stu-id="0647e-182">Open an elevated command line:</span></span>

    1. <span data-ttu-id="0647e-183">Passare a **Start** e digitare **cmd**.</span><span class="sxs-lookup"><span data-stu-id="0647e-183">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="0647e-184">Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="0647e-184">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="0647e-185">Immettere il comando indicato di seguito e premere **INVIO**:</span><span class="sxs-lookup"><span data-stu-id="0647e-185">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="0647e-186">Ad esempio: netsh winhttp set proxy 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="0647e-186">For example: netsh winhttp set proxy 10.0.0.6:8080</span></span>


###  <a name="proxy-configuration-for-down-level-devices"></a><span data-ttu-id="0647e-187">Configurazione proxy per i dispositivi di livello inferiore</span><span class="sxs-lookup"><span data-stu-id="0647e-187">Proxy Configuration for down-level devices</span></span>

<span data-ttu-id="0647e-188">i dispositivi Down-Level includono workstation Windows 7 SP1 e Windows 8.1, Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2 e versioni di Windows Server 2016 precedenti a Windows Server CB 1803.</span><span class="sxs-lookup"><span data-stu-id="0647e-188">Down-Level devices include Windows 7 SP1 and Windows 8.1 workstations as well as Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2, and versions of Windows Server 2016 prior to Windows Server CB 1803.</span></span> <span data-ttu-id="0647e-189">Questi sistemi operativi avranno il proxy configurato come parte di Microsoft Management Agent per gestire le comunicazioni dall'endpoint ad Azure.</span><span class="sxs-lookup"><span data-stu-id="0647e-189">These operating systems will have the proxy configured as part of the Microsoft Management Agent to handle communication from the endpoint to Azure.</span></span> <span data-ttu-id="0647e-190">Per informazioni sulla configurazione di un proxy in questi dispositivi, fare riferimento alla Guida alla distribuzione rapida di Microsoft Management Agent.</span><span class="sxs-lookup"><span data-stu-id="0647e-190">Refer to the Microsoft Management Agent Fast Deployment Guide for information on how a proxy is configured on these devices.</span></span>

### <a name="proxy-service-urls"></a><span data-ttu-id="0647e-191">URL del servizio proxy</span><span class="sxs-lookup"><span data-stu-id="0647e-191">Proxy Service URLs</span></span>
<span data-ttu-id="0647e-192">Gli URL che includono v20 in essi sono necessari solo se hai dispositivi Windows 10 versione 1803 o successiva.</span><span class="sxs-lookup"><span data-stu-id="0647e-192">URLs that include v20 in them are only needed if you have Windows 10, version 1803 or later devices.</span></span> <span data-ttu-id="0647e-193">Ad esempio, è necessario solo se il dispositivo è ```us-v20.events.data.microsoft.com``` Windows 10 versione 1803 o successiva.</span><span class="sxs-lookup"><span data-stu-id="0647e-193">For example, ```us-v20.events.data.microsoft.com``` is only needed if the device is on Windows 10, version 1803 or later.</span></span>
 

<span data-ttu-id="0647e-194">Se un proxy o un firewall blocca il traffico anonimo, poiché il sensore Microsoft Defender for Endpoint si connette dal contesto di sistema, assicurati che il traffico anonimo sia consentito negli URL elencati.</span><span class="sxs-lookup"><span data-stu-id="0647e-194">If a proxy or firewall is blocking anonymous traffic, as Microsoft Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the listed URLs.</span></span>

<span data-ttu-id="0647e-195">Nel seguente foglio di calcolo scaricabile sono elencati i servizi e gli URL associati a cui la rete deve essere in grado di connettersi.</span><span class="sxs-lookup"><span data-stu-id="0647e-195">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="0647e-196">Verificare che non siano presenti regole di filtro di rete o firewall che negherebbero l'accesso *a* questi URL oppure potrebbe essere necessario creare una regola di autorizzazione specifica per tali URL.</span><span class="sxs-lookup"><span data-stu-id="0647e-196">Ensure there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="0647e-197">**Foglio di calcolo dell'elenco dei domini**</span><span class="sxs-lookup"><span data-stu-id="0647e-197">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="0647e-198">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0647e-198">**Description**</span></span>|
|:-----|:-----|
|![Immagine di scorrimento per il foglio di calcolo degli URL di Microsoft Defender for Endpoint](images/mdatp-urls.png)<br/>  | <span data-ttu-id="0647e-200">Foglio di calcolo di record DNS specifici per le posizioni dei servizi, le posizioni geografiche e il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0647e-200">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="0647e-201">Scaricare il foglio di calcolo qui.</span><span class="sxs-lookup"><span data-stu-id="0647e-201">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


###  <a name="microsoft-defender-for-endpoint-service-backend-ip-ranges"></a><span data-ttu-id="0647e-202">Intervalli IP back-end di Microsoft Defender for Endpoint Service</span><span class="sxs-lookup"><span data-stu-id="0647e-202">Microsoft Defender for Endpoint service backend IP ranges</span></span>

<span data-ttu-id="0647e-203">Se i dispositivi di rete non supportano le regole basate su DNS, usa invece intervalli IP.</span><span class="sxs-lookup"><span data-stu-id="0647e-203">If your network devices don't support DNS-based rules, use IP ranges instead.</span></span>

<span data-ttu-id="0647e-204">Defender for Endpoint è creato nel cloud di Azure, distribuito nelle aree geografiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="0647e-204">Defender for Endpoint is built in Azure cloud, deployed in the following regions:</span></span>

- <span data-ttu-id="0647e-205">AzureCloud.eastus</span><span class="sxs-lookup"><span data-stu-id="0647e-205">AzureCloud.eastus</span></span>
- <span data-ttu-id="0647e-206">AzureCloud.eastus2</span><span class="sxs-lookup"><span data-stu-id="0647e-206">AzureCloud.eastus2</span></span>
- <span data-ttu-id="0647e-207">AzureCloud.westcentralus</span><span class="sxs-lookup"><span data-stu-id="0647e-207">AzureCloud.westcentralus</span></span>
- <span data-ttu-id="0647e-208">AzureCloud.northeurope</span><span class="sxs-lookup"><span data-stu-id="0647e-208">AzureCloud.northeurope</span></span>
- <span data-ttu-id="0647e-209">AzureCloud.westeurope</span><span class="sxs-lookup"><span data-stu-id="0647e-209">AzureCloud.westeurope</span></span>
- <span data-ttu-id="0647e-210">AzureCloud.uksouth</span><span class="sxs-lookup"><span data-stu-id="0647e-210">AzureCloud.uksouth</span></span>
- <span data-ttu-id="0647e-211">AzureCloud.ukwest</span><span class="sxs-lookup"><span data-stu-id="0647e-211">AzureCloud.ukwest</span></span>

<span data-ttu-id="0647e-212">Gli intervalli IP di Azure sono disponibili in [Intervalli IP di Azure e tag di servizio - Cloud pubblico.](https://www.microsoft.com/download/details.aspx?id=56519)</span><span class="sxs-lookup"><span data-stu-id="0647e-212">You can find the Azure IP ranges in [Azure IP Ranges and Service Tags – Public Cloud](https://www.microsoft.com/download/details.aspx?id=56519).</span></span>

> [!NOTE]
> <span data-ttu-id="0647e-213">Come soluzione basata sul cloud, gli intervalli di indirizzi IP possono cambiare.</span><span class="sxs-lookup"><span data-stu-id="0647e-213">As a cloud-based solution, the IP address ranges can change.</span></span> <span data-ttu-id="0647e-214">È consigliabile passare a regole basate su DNS.</span><span class="sxs-lookup"><span data-stu-id="0647e-214">It's recommended you move to DNS-based rules.</span></span>

> [!NOTE]
> <span data-ttu-id="0647e-215">If you are a US Government customer, please see the corresponding section in the [Defender for Endpoint for US Government](gov.md#service-backend-ip-ranges) page.</span><span class="sxs-lookup"><span data-stu-id="0647e-215">If you are a US Government customer, please see the corresponding section in the [Defender for Endpoint for US Government](gov.md#service-backend-ip-ranges) page.</span></span>

## <a name="next-step"></a><span data-ttu-id="0647e-216">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="0647e-216">Next step</span></span>

<span data-ttu-id="0647e-217">![**Fase 3: onboard**](images/onboard.png)</span><span class="sxs-lookup"><span data-stu-id="0647e-217">![**Phase 3: Onboard**](images/onboard.png)</span></span> <br><span data-ttu-id="0647e-218">[Fase 3: onboard: onboard](onboarding.md)dei dispositivi al servizio in modo che il servizio Microsoft Defender for Endpoint possa ottenere i dati del sensore da essi.</span><span class="sxs-lookup"><span data-stu-id="0647e-218">[Phase 3: Onboard](onboarding.md): Onboard devices to the service so that the Microsoft Defender for Endpoint service can get sensor data from them.</span></span> 
