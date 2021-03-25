---
title: Configurazione del proxy del dispositivo e delle impostazioni di connessione Internet per la prevenzione della perdita di dati degli endpoint
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Informazioni su come configurare il proxy del dispositivo e le impostazioni di connessione Internet per la prevenzione della perdita di dati degli endpoint.
ms.openlocfilehash: 4d1aa3b75ec0a0720f3d92c847bf7c6cde6d966f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199275"
---
# <a name="configure-device-proxy-and-internet-connection-settings-for-endpoint-dlp"></a><span data-ttu-id="9b690-103">Configurazione del proxy del dispositivo e delle impostazioni di connessione Internet per la prevenzione della perdita di dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="9b690-103">Configure device proxy and internet connection settings for Endpoint DLP</span></span>

<span data-ttu-id="9b690-104">La Prevenzione della perdita dei dati degli endpoint Microsoft usa Microsoft Windows HTTP (WinHTTP) per segnalare i dati e comunicare con il servizio cloud degli endpoint Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9b690-104">Microsoft Endpoint DLP uses Microsoft Windows HTTP (WinHTTP) to report data and communicate with the Microsoft endpoint cloud service.</span></span> <span data-ttu-id="9b690-105">La Prevenzione della perdita dei dati degli endpoint integrata viene eseguita nel sistema attraverso l'account LocalSystem.</span><span class="sxs-lookup"><span data-stu-id="9b690-105">The embedded Endpoint DLP runs in system context using the LocalSystem account.</span></span>

> [!TIP]
> <span data-ttu-id="9b690-106">Per le organizzazioni che usano i proxy come porta di accesso a Internet, è possibile usare la protezione della rete per esaminare gli eventi che si verificano dietro un proxy.</span><span class="sxs-lookup"><span data-stu-id="9b690-106">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="9b690-107">Per altre informazioni, vedere [Esaminare gli eventi di connessione che si verificano dietro i proxy di inoltro](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy).</span><span class="sxs-lookup"><span data-stu-id="9b690-107">For more information, see [Investigate connection events that occur behind forward proxies](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy).</span></span>

<span data-ttu-id="9b690-108">L'impostazione di configurazione WinHTTP è indipendente dalle impostazioni del proxy di esplorazione Internet (WinINet) di Windows Internet e può solo individuare un server proxy usando i metodi di individuazione automatica seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b690-108">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following auto discovery methods:</span></span>

- <span data-ttu-id="9b690-109">Proxy trasparente</span><span class="sxs-lookup"><span data-stu-id="9b690-109">Transparent proxy</span></span>
- <span data-ttu-id="9b690-110">Protocollo Web Proxy Auto-discovery (WPAD)</span><span class="sxs-lookup"><span data-stu-id="9b690-110">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

> [!NOTE]
> <span data-ttu-id="9b690-111">Se nella topologia di rete si usa un proxy trasparente o WPAD, non sono necessarie impostazioni di configurazione speciali.</span><span class="sxs-lookup"><span data-stu-id="9b690-111">If you’re using Transparent proxy or WPAD in your network topology, you don’t need special configuration settings.</span></span> <span data-ttu-id="9b690-112">Per ulteriori informazioni sulle esclusioni URL nel proxy di Microsoft Defender per Endpoint, vedere [Abilitare l'accesso agli URL del servizio cloud della Prevenzione della perdita dei dati degli endpoint nel server proxy](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="9b690-112">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Endpoint DLP cloud service URLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="9b690-113">Configurazione manuale del proxy statico:</span><span class="sxs-lookup"><span data-stu-id="9b690-113">Manual static proxy configuration:</span></span>
    - <span data-ttu-id="9b690-114">Configurazione basata sul registro</span><span class="sxs-lookup"><span data-stu-id="9b690-114">Registry-based configuration</span></span>
    - <span data-ttu-id="9b690-115">WinHTTP configurato utilizzando il comando netsh. Questo è adatto solo per desktop in una topologia stabile (ad esempio: un desktop in una rete aziendale dietro lo stesso proxy)</span><span class="sxs-lookup"><span data-stu-id="9b690-115">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="9b690-116">Configurare manualmente il server proxy con un proxy statico basato sul registro</span><span class="sxs-lookup"><span data-stu-id="9b690-116">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="9b690-117">Per i dispositivi endpoint a cui non è consentito connettersi a Internet, è necessario configurare un proxy statico basato sul registro.</span><span class="sxs-lookup"><span data-stu-id="9b690-117">For endpoint devices that aren't permitted to connect to the Internet, you need to configure a registry-based static proxy.</span></span> <span data-ttu-id="9b690-118">È necessario configurarlo per consentire solo alla Prevenzione della perdita dei dati degli endpoint di Microsoft di segnalare i dati di diagnostica e comunicare con il servizio cloud di endpoint Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9b690-118">You need to configure this to allow only Microsoft Endpoint DLP to report diagnostic data and communicate with Microsoft endpoint cloud service.</span></span>

<span data-ttu-id="9b690-119">Il proxy statico è configurabile tramite Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="9b690-119">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="9b690-120">I criteri di gruppo sono disponibili in:</span><span class="sxs-lookup"><span data-stu-id="9b690-120">The group policy can be found under:</span></span>

1. <span data-ttu-id="9b690-121">Aprire **Modelli amministrativi > Componenti di Windows > Raccolta dati e build di anteprima > Configura l'utilizzo del proxy autenticato per l'esperienza utente connessa e servizio di telemetria**</span><span class="sxs-lookup"><span data-stu-id="9b690-121">Open **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**</span></span>

2. <span data-ttu-id="9b690-122">Impostarlo su **Abilitato** e selezionare **Disabilita uso proxy autenticato**:</span><span class="sxs-lookup"><span data-stu-id="9b690-122">Set it to **Enabled** and select **Disable Authenticated Proxy usage**:</span></span> 

![Immagine delle impostazioni di criteri di gruppo 1](../media/atp-gpo-proxy1.png)
 
3. <span data-ttu-id="9b690-124">Aprire **Modelli amministrativi > Componenti di Windows > Raccolta dati e build di anteprima > Configura esperienze utente connesse e telemetria**:</span><span class="sxs-lookup"><span data-stu-id="9b690-124">Open **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>

 <span data-ttu-id="9b690-125">Configurare il proxy inverso</span><span class="sxs-lookup"><span data-stu-id="9b690-125">Configure the proxy</span></span>

![Immagine delle impostazioni di criteri di gruppo 2](../media/atp-gpo-proxy2.png)

<span data-ttu-id="9b690-127">Il criterio imposta due valori di registro`TelemetryProxyServer` come REG_SZ e `DisableEnterpriseAuthProxy` REG_DWORD nella chiave di registro`HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span><span class="sxs-lookup"><span data-stu-id="9b690-127">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

<span data-ttu-id="9b690-128">Il valore di registro TelemetryProxyServer è nel formato \<server name or ip\>:\<port\>.</span><span class="sxs-lookup"><span data-stu-id="9b690-128">The registry value TelemetryProxyServer is in this format \<server name or ip\>:\<port\>.</span></span> <span data-ttu-id="9b690-129">Ad esempio: **10.0.0.6:8080**</span><span class="sxs-lookup"><span data-stu-id="9b690-129">For example: **10.0.0.6:8080**</span></span>

<span data-ttu-id="9b690-130">Il valore del registro `DisableEnterpriseAuthProxy` deve essere impostato su 1.</span><span class="sxs-lookup"><span data-stu-id="9b690-130">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="9b690-131">Configurare manualmente il server proxy con il comando "netsh"</span><span class="sxs-lookup"><span data-stu-id="9b690-131">Configure the proxy server manually using "netsh" command</span></span>

<span data-ttu-id="9b690-132">Usare netsh per configurare un proxy statico a livello di sistema.</span><span class="sxs-lookup"><span data-stu-id="9b690-132">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> <span data-ttu-id="9b690-133">Questa operazione avrà effetto su tutte le applicazioni, inclusi i servizi di Windows che usano WinHTTP con proxy predefinito.</span><span class="sxs-lookup"><span data-stu-id="9b690-133">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span> <span data-ttu-id="9b690-134">I portatili che stanno cambiando la topologia, ad esempio da Office a Home, non funzioneranno con netsh.</span><span class="sxs-lookup"><span data-stu-id="9b690-134">- Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="9b690-135">È consigliabile usare la configurazione del proxy statico basata sul registro.</span><span class="sxs-lookup"><span data-stu-id="9b690-135">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="9b690-136">Aprire un prompt dei comandi con privilegi elevati:</span><span class="sxs-lookup"><span data-stu-id="9b690-136">Open an elevated command line:</span></span>
    1. <span data-ttu-id="9b690-137">Passare a **Start** e digitare **cmd**</span><span class="sxs-lookup"><span data-stu-id="9b690-137">Go to **Start** and type **cmd**</span></span>
    1. <span data-ttu-id="9b690-138">Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="9b690-138">Right-click **Command prompt** and select **Run as administrator**.</span></span>
2.  <span data-ttu-id="9b690-139">Immettere il comando indicato di seguito e premere **INVIO**:</span><span class="sxs-lookup"><span data-stu-id="9b690-139">Enter the following command and press **Enter**:</span></span>

    `netsh winhttp set proxy <proxy>:<port>`

    <span data-ttu-id="9b690-140">Ad esempio: **netsh winhttp set proxy 10.0.0.6:8080**</span><span class="sxs-lookup"><span data-stu-id="9b690-140">For example: **netsh winhttp set proxy 10.0.0.6:8080**</span></span>

3. <span data-ttu-id="9b690-141">Per reimpostare il proxy winhttp, immettere il comando indicato di seguito e premere **INVIO**:</span><span class="sxs-lookup"><span data-stu-id="9b690-141">To reset the winhttp proxy, enter the following command and press **Enter**:</span></span>

     `netsh winhttp reset proxy`

<span data-ttu-id="9b690-142">Per altre informazioni, vedere [Sintassi comando netsh, contesti e formattazione](/windows-server/networking/technologies/netsh/netsh-contexts).</span><span class="sxs-lookup"><span data-stu-id="9b690-142">See [Netsh Command Syntax, Contexts, and Formatting](/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>


## <a name="enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server"></a><span data-ttu-id="9b690-143">Abilitare l'accesso agli URL del servizio cloud della Prevenzione della perdita dei dati degli endpoint nel server proxy</span><span class="sxs-lookup"><span data-stu-id="9b690-143">Enable access to Endpoint DLP cloud service URLs in the proxy server</span></span>

<span data-ttu-id="9b690-144">Se un proxy o un firewall blocca tutto il traffico per impostazione predefinita e consente solo domini specifici, aggiungere i domini elencati nel foglio di lavoro scaricabile all'elenco di domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="9b690-144">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="9b690-145">Il [foglio di calcolo scaricabile](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) elenca i servizi e gli URL associati a cui la rete deve essere in grado di connettersi.</span><span class="sxs-lookup"><span data-stu-id="9b690-145">This [downloadable spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="9b690-146">È necessario assicurarsi che non ci siano regole di filtro di rete o firewall che neghino l'accesso a questi URL, altrimenti potrebbe essere necessario creare una regola specifica per consentirgli l’accesso.</span><span class="sxs-lookup"><span data-stu-id="9b690-146">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an allow rule specifically for them.</span></span>

<span data-ttu-id="9b690-147">Se un proxy o un firewall ha l’analisi HTTPS (ispezione SSL) abilitata, bisogna escludere i domini elencati nella tabella di analisi HTTPS di cui sopra.</span><span class="sxs-lookup"><span data-stu-id="9b690-147">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>
<span data-ttu-id="9b690-148">Se un proxy o un firewall blocca il traffico anonimo, perché la Prevenzione della perdita dei dati degli endpoint si connette dal contesto di sistema, assicurarsi che il traffico anonimo sia consentito negli URL elencati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="9b690-148">If a proxy or firewall is blocking anonymous traffic, as Endpoint DLP is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

## <a name="verify-client-connectivity-to-microsoft-cloud-service-urls"></a><span data-ttu-id="9b690-149">Verificare la connettività client agli URL dei servizi cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9b690-149">Verify client connectivity to Microsoft cloud service URLs</span></span>

<span data-ttu-id="9b690-150">Verificare che la configurazione del proxy sia stata completata correttamente, che WinHTTP possa individuare e comunicare attraverso il server proxy nell’ambiente e che il server proxy consenta il traffico agli URL del servizio Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="9b690-150">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="9b690-151">Scaricare lo[strumento MDATP Client Analyzer](https://aka.ms/mdatpanalyzer) nel PC in cui è in esecuzione la Prevenzione della perdita dei dati degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="9b690-151">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Endpoint DLP is running on.</span></span>
2. <span data-ttu-id="9b690-152">Estrarre il contenuto di MDATPClientAnalyzer.zip nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9b690-152">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>
3. <span data-ttu-id="9b690-153">Aprire un prompt dei comandi con privilegi elevati:</span><span class="sxs-lookup"><span data-stu-id="9b690-153">Open an elevated command line:</span></span>
    1. <span data-ttu-id="9b690-154">Passare a **Start** e digitare **cmd**.</span><span class="sxs-lookup"><span data-stu-id="9b690-154">Go to **Start** and type **cmd**.</span></span>
    1. <span data-ttu-id="9b690-155">Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="9b690-155">Right-click **Command prompt** and select **Run as administrator**.</span></span>
4.  <span data-ttu-id="9b690-156">Immettere il comando indicato di seguito e premere **INVIO**:</span><span class="sxs-lookup"><span data-stu-id="9b690-156">Enter the following command and press **Enter**:</span></span>
    
`HardDrivePath\MDATPClientAnalyzer.cmd`

<span data-ttu-id="9b690-157">Sostituire *HardDrivePath* con il percorso in cui è stato scaricato lo strumento MDATPClientAnalyzer, ad esempio</span><span class="sxs-lookup"><span data-stu-id="9b690-157">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example</span></span>
    
<span data-ttu-id="9b690-158">**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**</span><span class="sxs-lookup"><span data-stu-id="9b690-158">**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**</span></span>


5.  <span data-ttu-id="9b690-159">Estrarre il file **MDATPClientAnalyzerResult. zip** creato dallo strumento nella cartella usata in _HardDrivePath\*.</span><span class="sxs-lookup"><span data-stu-id="9b690-159">Extract the **MDATPClientAnalyzerResult.zip** _ file created by tool in the folder used in the _HardDrivePath\*.</span></span>

6.  <span data-ttu-id="9b690-160">Aprire **MDATPClientAnalyzerResult.txt** e verificare di avere eseguito la procedura di configurazione del proxy per abilitare l'individuazione del server e l'accesso agli URL di servizio.</span><span class="sxs-lookup"><span data-stu-id="9b690-160">Open **MDATPClientAnalyzerResult.txt** and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span>  <span data-ttu-id="9b690-161">Lo strumento controlla la connettività degli URL del servizio Defender per Endpoint con cui è configurato per interagire.</span><span class="sxs-lookup"><span data-stu-id="9b690-161">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="9b690-162">Quindi immette i risultati per ogni URL che potrebbe essere potenzialmente utilizzato per comunicare con il servizio Defender per l'endpoint nel file **MDATPClientAnalyzerResult.txt**.</span><span class="sxs-lookup"><span data-stu-id="9b690-162">It then prints the results into the **MDATPClientAnalyzerResult.txt** file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="9b690-163">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9b690-163">For example:</span></span>

    <span data-ttu-id="9b690-164">**Testing URL: https://xxx.microsoft.com/xxx </br> 1 - Default proxy: Succeeded (200) </br> 2 - Proxy auto discovery (WPAD): Succeeded (200)</br> 3 - Proxy disabled: Succeeded (200)</br> 4 - Named proxy: Doesn't exist</br> 5 - Command-line proxy: Doesn't exist**</span><span class="sxs-lookup"><span data-stu-id="9b690-164">**Testing URL: https://xxx.microsoft.com/xxx </br> 1 - Default proxy: Succeeded (200) </br> 2 - Proxy auto discovery (WPAD): Succeeded (200)</br> 3 - Proxy disabled: Succeeded (200)</br> 4 - Named proxy: Doesn't exist</br> 5 - Command-line proxy: Doesn't exist**</span></span></br>


<span data-ttu-id="9b690-165">Se almeno una delle opzioni di connettività restituisce uno stato (200), il client Defender per Endpoint può comunicare correttamente con l'URL testato usando questo metodo di connettività.</span><span class="sxs-lookup"><span data-stu-id="9b690-165">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span> 

<span data-ttu-id="9b690-166">Tuttavia, se i risultati della verifica della connettività indicano un errore, viene visualizzato un errore HTTP (vedere codici di stato HTTP).</span><span class="sxs-lookup"><span data-stu-id="9b690-166">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="9b690-167">È quindi possibile usare gli URL nella tabella illustrata in [Abilitare l'accesso agli URL del servizio cloud della Prevenzione della perdita dei dati degli endpoint nel server proxy](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="9b690-167">You can then use the URLs in the table shown in [Enable access to Endpoint DLP cloud service URLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="9b690-168">Gli URL usati variano a seconda dell'area selezionata durante la procedura di onboarding.</span><span class="sxs-lookup"><span data-stu-id="9b690-168">The URLs you’ll use will depend on the region selected during the onboarding procedure.</span></span>
[!NOTE]<span data-ttu-id="9b690-169"> Strumento di analisi della connettività non è compatibile con la regola ASR [Bloccare le creazioni di processi provenienti dai comandi PSExec e WMI](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="9b690-169"> The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="9b690-170">È necessario disabilitare temporaneamente questa regola per eseguire lo strumento di connettività.</span><span class="sxs-lookup"><span data-stu-id="9b690-170">You will need to temporarily disable this rule to run the connectivity tool.</span></span>

[!NOTE] <span data-ttu-id="9b690-171">Quando TelemetryProxyServer è impostato, nel Registro o tramite Criteri di Gruppo, Defender for Endpoint ricade in modalità diretta se non può accedere al proxy definito.</span><span class="sxs-lookup"><span data-stu-id="9b690-171">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can’t access the defined proxy.</span></span>
<span data-ttu-id="9b690-172">Argomenti correlati •   Onboarding di dispositivi Windows 10 •   Risolvere i problemi di onboarding della Microsoft Prevenzione della perdita dei dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="9b690-172">Related topics •   Onboard Windows 10 devices •   Troubleshoot Microsoft Endpoint DLP onboarding issues</span></span>





## <a name="see-also"></a><span data-ttu-id="9b690-173">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b690-173">See also</span></span>

- [<span data-ttu-id="9b690-174">Informazioni sulla prevenzione della perdita di dati degli endpoint </span><span class="sxs-lookup"><span data-stu-id="9b690-174">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="9b690-175">Uso della Prevenzione della perdita di dati degli endpoint </span><span class="sxs-lookup"><span data-stu-id="9b690-175">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="9b690-176">Panoramica sulla prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="9b690-176">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="9b690-177">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="9b690-177">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="9b690-178">Introduzione a Esplora attività</span><span class="sxs-lookup"><span data-stu-id="9b690-178">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="9b690-179">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="9b690-179">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="9b690-180">Strumenti e metodi di onboarding per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="9b690-180">Onboarding tools and methods for Windows 10 machines</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="9b690-181">Abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9b690-181">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="9b690-182">Dispositivi aggiunti ad Azure AD</span><span class="sxs-lookup"><span data-stu-id="9b690-182">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="9b690-183">Scaricare il nuovo Microsoft Edge basato su Chromium</span><span class="sxs-lookup"><span data-stu-id="9b690-183">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)