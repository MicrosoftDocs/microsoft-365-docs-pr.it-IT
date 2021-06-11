---
title: Microsoft Defender per endpoint
description: Microsoft Defender for Endpoint è una piattaforma di sicurezza degli endpoint aziendale che aiuta a difendersi dalle minacce persistenti avanzate.
keywords: introduzione a Microsoft Defender for Endpoint, introduzione a Microsoft Defender for Endpoint, cybersecurity, minacce persistenti avanzate, sicurezza aziendale, sensore comportamentale del computer, sicurezza cloud, analisi, intelligence sulle minacce, riduzione della superficie di attacco, protezione di nuova generazione, analisi e correzione automatizzate, esperti di minacce Microsoft, punteggio sicuro, ricerca avanzata, Microsoft 365 Defender, ricerca di minacce informatiche
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 23a9b99a71d700bdeddb3398c592eeb778ceef23
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879265"
---
# <a name="microsoft-defender-for-endpoint"></a><span data-ttu-id="14889-104">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="14889-104">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="14889-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="14889-105">**Applies to:**</span></span>
- [<span data-ttu-id="14889-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="14889-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="14889-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="14889-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="14889-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="14889-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="14889-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="14889-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> <span data-ttu-id="14889-110">Per altre info sulle funzionalità Windows 10 Enterprise Edition, vedi [Windows 10 Enterprise Edition.](https://www.microsoft.com/WindowsForBusiness/buy)</span><span class="sxs-lookup"><span data-stu-id="14889-110">For more info about Windows 10 Enterprise Edition features and functionality, see [Windows 10 Enterprise edition](https://www.microsoft.com/WindowsForBusiness/buy).</span></span>

<span data-ttu-id="14889-111">Microsoft Defender for Endpoint è una piattaforma di sicurezza degli endpoint aziendale progettata per aiutare le reti aziendali a prevenire, rilevare, analizzare e rispondere alle minacce avanzate.</span><span class="sxs-lookup"><span data-stu-id="14889-111">Microsoft Defender for Endpoint is an enterprise endpoint security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.</span></span>
<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

<span data-ttu-id="14889-112">Defender for Endpoint usa la seguente combinazione di tecnologia incorporata Windows 10 e il solido servizio cloud di Microsoft:</span><span class="sxs-lookup"><span data-stu-id="14889-112">Defender for Endpoint uses the following combination of technology built into Windows 10 and Microsoft's robust cloud service:</span></span>

-   <span data-ttu-id="14889-113">**Sensori comportamentali** endpoint: incorporati in Windows 10, questi sensori raccolgono ed elaborano i segnali comportamentali dal sistema operativo e inviano i dati del sensore all'istanza cloud privata, isolata di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="14889-113">**Endpoint behavioral sensors**: Embedded in Windows 10, these sensors collect and process behavioral signals from the operating system and send this sensor data to your private, isolated, cloud instance of Microsoft Defender for Endpoint.</span></span>


-   <span data-ttu-id="14889-114">Analisi della sicurezza **cloud:** utilizzo di big data, apprendimento dei dispositivi e ottica Microsoft univoca nell'ecosistema di Windows, prodotti cloud aziendali (ad esempio Office 365) e asset online, i segnali comportamentali vengono tradotti in dati analitici, rilevamenti e risposte consigliate alle minacce avanzate.</span><span class="sxs-lookup"><span data-stu-id="14889-114">**Cloud security analytics**: Leveraging big-data, device-learning, and unique Microsoft optics across the Windows ecosystem, enterprise cloud products (such as Office 365), and online assets, behavioral signals are translated into insights, detections, and recommended responses to advanced threats.</span></span>

-   <span data-ttu-id="14889-115">**Intelligence** per le minacce: generata da microsoft, team di sicurezza e aumentata dall'intelligence per le minacce fornita dai partner, l'intelligence per le minacce consente a Defender for Endpoint di identificare strumenti, tecniche e procedure dell'utente malintenzionato e generare avvisi quando vengono osservati nei dati dei sensori raccolti.</span><span class="sxs-lookup"><span data-stu-id="14889-115">**Threat intelligence**: Generated by Microsoft hunters, security teams, and augmented by threat intelligence provided by partners, threat intelligence enables Defender for Endpoint to identify attacker tools, techniques, and procedures, and generate alerts when they are observed in collected sensor data.</span></span>

<center><h2><span data-ttu-id="14889-116">Microsoft Defender per endpoint</center></span><span class="sxs-lookup"><span data-stu-id="14889-116">Microsoft Defender for Endpoint</center></span></span></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><span data-ttu-id="14889-117"><b>Gestione delle & delle minacce</b></center></a></span><span class="sxs-lookup"><span data-stu-id="14889-117"><b>Threat & Vulnerability Management</b></center></a></span></span></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><span data-ttu-id="14889-118"><b>Riduzione della superficie di attacco</b></center></a></span><span class="sxs-lookup"><span data-stu-id="14889-118"><b>Attack surface reduction</b></center></a></span></span></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <span data-ttu-id="14889-119"><b>Protezione di nuova generazione</b></a></center></span><span class="sxs-lookup"><span data-stu-id="14889-119"><b>Next-generation protection</b></a></center></span></span></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <span data-ttu-id="14889-120"><b>Rilevamento e risposta degli endpoint</b></a></center></span><span class="sxs-lookup"><span data-stu-id="14889-120"><b>Endpoint detection and response</b></a></center></span></span></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <span data-ttu-id="14889-121"><b>Analisi e correzione automatizzate</b></a></center></span><span class="sxs-lookup"><span data-stu-id="14889-121"><b>Automated investigation and remediation</b></a></center></span></span></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <span data-ttu-id="14889-122"><b>Microsoft Threat Experts</b></a></center></span><span class="sxs-lookup"><span data-stu-id="14889-122"><b>Microsoft Threat Experts</b></a></center></span></span></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="14889-123">
<a href="#apis"><center><b>Configurazione e amministrazione centralizzate, API</a></span><span class="sxs-lookup"><span data-stu-id="14889-123">
<a href="#apis"><center><b>Centralized configuration and administration, APIs</a></span></span></b></center></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="14889-124"><a href="#mtp"><center><b>Microsoft 365 Defender</a></span><span class="sxs-lookup"><span data-stu-id="14889-124"><a href="#mtp"><center><b>Microsoft 365 Defender</a></span></span></center></b></td>
</tr>
</table>
<br>

<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0] 

> [!TIP]
> - <span data-ttu-id="14889-125">Informazioni sui miglioramenti più recenti in Defender for Endpoint: [Novità di Microsoft Defender per Endpoint.](whats-new-in-microsoft-defender-atp.md)</span><span class="sxs-lookup"><span data-stu-id="14889-125">Learn about the latest enhancements in Defender for Endpoint: [What's new in Microsoft Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>
> - <span data-ttu-id="14889-126">Microsoft Defender for Endpoint ha dimostrato le funzionalità di ottica e rilevamento leader del settore nella recente valutazione MITRE.</span><span class="sxs-lookup"><span data-stu-id="14889-126">Microsoft Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="14889-127">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="14889-127">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<a name="tvm"></a>

<span data-ttu-id="14889-128">**[Gestione delle & delle minacce](next-gen-threat-and-vuln-mgt.md)**</span><span class="sxs-lookup"><span data-stu-id="14889-128">**[Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md)**</span></span><br>
<span data-ttu-id="14889-129">Questa funzionalità incorporata usa un approccio basato sul rischio che cambia il gioco per l'individuazione, la definizione delle priorità e la correzione delle vulnerabilità degli endpoint e delle configurazioni erre.</span><span class="sxs-lookup"><span data-stu-id="14889-129">This built-in capability uses a game-changing risk-based approach to the discovery, prioritization, and remediation of endpoint vulnerabilities and misconfigurations.</span></span> 

<a name="asr"></a>

<span data-ttu-id="14889-130">**[Riduzione della superficie di attacco](overview-attack-surface-reduction.md)**</span><span class="sxs-lookup"><span data-stu-id="14889-130">**[Attack surface reduction](overview-attack-surface-reduction.md)**</span></span><br>
<span data-ttu-id="14889-131">Il set di funzionalità di riduzione della superficie di attacco fornisce la prima linea di difesa nello stack.</span><span class="sxs-lookup"><span data-stu-id="14889-131">The attack surface reduction set of capabilities provides the first line of defense in the stack.</span></span> <span data-ttu-id="14889-132">Garantendo che le impostazioni di configurazione siano impostate correttamente e che le tecniche di mitigazione degli exploit siano applicate, le funzionalità resistono agli attacchi e allo sfruttamento.</span><span class="sxs-lookup"><span data-stu-id="14889-132">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, the capabilities resist attacks and exploitation.</span></span> <span data-ttu-id="14889-133">Questo set di [](network-protection.md) funzionalità include anche la protezione di rete e la protezione [Web,](web-protection-overview.md)che regolano l'accesso a indirizzi IP, domini e URL dannosi.</span><span class="sxs-lookup"><span data-stu-id="14889-133">This set of capabilities also includes [network protection](network-protection.md) and [web protection](web-protection-overview.md), which regulate access to malicious IP addresses, domains, and URLs.</span></span> 

<a name="ngp"></a>

<span data-ttu-id="14889-134">**[Protezione di nuova generazione](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span><span class="sxs-lookup"><span data-stu-id="14889-134">**[Next-generation protection](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span></span><br>
<span data-ttu-id="14889-135">Per rafforzare ulteriormente il perimetro di sicurezza della rete, Microsoft Defender for Endpoint usa una protezione di nuova generazione progettata per rilevare tutti i tipi di minacce emergenti.</span><span class="sxs-lookup"><span data-stu-id="14889-135">To further reinforce the security perimeter of your network, Microsoft Defender for Endpoint uses next-generation protection designed to catch all types of emerging threats.</span></span>

<a name="edr"></a>

<span data-ttu-id="14889-136">**[Rilevamento e risposta di endpoint](overview-endpoint-detection-response.md)**</span><span class="sxs-lookup"><span data-stu-id="14889-136">**[Endpoint detection and response](overview-endpoint-detection-response.md)**</span></span><br>
<span data-ttu-id="14889-137">Le funzionalità di rilevamento e risposta degli endpoint vengono messe in atto per rilevare, analizzare e rispondere alle minacce avanzate che potrebbero aver fatto superare i primi due pilastri della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="14889-137">Endpoint detection and response capabilities are put in place to detect, investigate, and respond to advanced threats that may have made it past the first two security pillars.</span></span> <span data-ttu-id="14889-138">[La ricerca avanzata](advanced-hunting-overview.md) offre uno strumento di ricerca delle minacce basato su query che consente di individuare in modo proattivo le violazioni e creare rilevamenti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="14889-138">[Advanced hunting](advanced-hunting-overview.md) provides a query-based threat-hunting tool that lets you proactively find breaches and create custom detections.</span></span>

<a name="ai"></a>

<span data-ttu-id="14889-139">**[Analisi e correzione automatizzate](automated-investigations.md)**</span><span class="sxs-lookup"><span data-stu-id="14889-139">**[Automated investigation and remediation](automated-investigations.md)**</span></span><br>
<span data-ttu-id="14889-140">Oltre a essere in grado di rispondere rapidamente agli attacchi avanzati, Microsoft Defender for Endpoint offre funzionalità di analisi e correzione automatiche che consentono di ridurre il volume di avvisi in minuti su larga scala.</span><span class="sxs-lookup"><span data-stu-id="14889-140">In conjunction with being able to quickly respond to advanced attacks, Microsoft Defender for Endpoint offers automatic investigation and remediation capabilities that help reduce the volume of alerts in minutes at scale.</span></span> 

<a name="ss"></a>

<span data-ttu-id="14889-141">**[Punteggio di sicurezza Microsoft per dispositivi](tvm-microsoft-secure-score-devices.md)**</span><span class="sxs-lookup"><span data-stu-id="14889-141">**[Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md)**</span></span><br>

<span data-ttu-id="14889-142">Defender for Endpoint include Microsoft Secure Score for Devices per aiutarti a valutare in modo dinamico lo stato di sicurezza della rete aziendale, identificare i sistemi non protetti ed eseguire azioni consigliate per migliorare la sicurezza complessiva dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="14889-142">Defender for Endpoint includes Microsoft Secure Score for Devices to help you dynamically assess the security state of your enterprise network, identify unprotected systems, and take recommended actions to improve the overall security of your organization.</span></span>

<a name="mte"></a>

<span data-ttu-id="14889-143">**[Microsoft Threat Experts](microsoft-threat-experts.md)**</span><span class="sxs-lookup"><span data-stu-id="14889-143">**[Microsoft Threat Experts](microsoft-threat-experts.md)**</span></span><br>
<span data-ttu-id="14889-144">Il nuovo servizio di ricerca delle minacce gestite di Microsoft Defender for Endpoint fornisce la ricerca proattiva, la definizione delle priorità e ulteriori informazioni e contesto che consentono ai Centri operazioni di sicurezza (SOC) di identificare e rispondere alle minacce in modo rapido e accurato.</span><span class="sxs-lookup"><span data-stu-id="14889-144">Microsoft Defender for Endpoint's new managed threat hunting service provides proactive hunting, prioritization, and additional context and insights that further empower Security operation centers (SOCs) to identify and respond to threats quickly and accurately.</span></span>

>[!IMPORTANT]
><span data-ttu-id="14889-145">I clienti di Defender for Endpoint devono richiedere il servizio Microsoft Threat Experts di ricerca delle minacce gestite per ottenere notifiche di attacco mirato proattive e collaborare con esperti su richiesta.</span><span class="sxs-lookup"><span data-stu-id="14889-145">Defender for Endpoint customers need to apply for the Microsoft Threat Experts managed threat hunting service to get proactive Targeted Attack Notifications and to collaborate with experts on demand.</span></span> <span data-ttu-id="14889-146">Experts on Demand è un servizio di componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="14889-146">Experts on Demand is an add-on service.</span></span> <span data-ttu-id="14889-147">Le notifiche di attacco mirato vengono sempre incluse dopo essere state accettate Microsoft Threat Experts servizio di ricerca delle minacce gestite.</span><span class="sxs-lookup"><span data-stu-id="14889-147">Targeted Attack Notifications are always included after you have been accepted into Microsoft Threat Experts managed threat hunting service.</span></span><p>
><p><span data-ttu-id="14889-148">Se non si è ancora registrati e si desidera <b></b> sperimentarne i vantaggi, passare a Impostazioni > <b>funzionalità</b> > <b></b> > <b>avanzate Microsoft Threat Experts</b> da applicare.</span><span class="sxs-lookup"><span data-stu-id="14889-148">If you are not enrolled yet and would like to experience its benefits, go to <b>Settings</b> > <b>General</b> > <b>Advanced features</b> > <b>Microsoft Threat Experts</b> to apply.</span></span> <span data-ttu-id="14889-149">Una volta accettato, potrai ottenere i vantaggi delle notifiche di attacco mirato e avviare una versione di valutazione di 90 giorni di Experts on Demand.</span><span class="sxs-lookup"><span data-stu-id="14889-149">Once accepted, you will get the benefits of Targeted Attack Notifications, and start a  90-day trial of Experts on Demand.</span></span> <span data-ttu-id="14889-150">Contattare il rappresentante Microsoft per ottenere un abbonamento completo a Experts on Demand.</span><span class="sxs-lookup"><span data-stu-id="14889-150">Contact your Microsoft representative to get a full Experts on Demand subscription.</span></span>

<a name="apis"></a>

<span data-ttu-id="14889-151">**[Configurazione e amministrazione centralizzate, API](management-apis.md)**</span><span class="sxs-lookup"><span data-stu-id="14889-151">**[Centralized configuration and administration, APIs](management-apis.md)**</span></span><br>
<span data-ttu-id="14889-152">Integrare Microsoft Defender for Endpoint nei flussi di lavoro esistenti.</span><span class="sxs-lookup"><span data-stu-id="14889-152">Integrate Microsoft Defender for Endpoint into your existing workflows.</span></span>

<a name="mtp"></a>

<span data-ttu-id="14889-153">**[Integrazione con soluzioni Microsoft](threat-protection-integration.md)**</span><span class="sxs-lookup"><span data-stu-id="14889-153">**[Integration with Microsoft solutions](threat-protection-integration.md)**</span></span> <br>
<span data-ttu-id="14889-154">Defender for Endpoint si integra direttamente con varie soluzioni Microsoft, tra cui:</span><span class="sxs-lookup"><span data-stu-id="14889-154">Defender for Endpoint directly integrates with various Microsoft solutions, including:</span></span>
- <span data-ttu-id="14889-155">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="14889-155">Azure Defender</span></span>
- <span data-ttu-id="14889-156">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="14889-156">Azure Sentinel</span></span>
- <span data-ttu-id="14889-157">Intune</span><span class="sxs-lookup"><span data-stu-id="14889-157">Intune</span></span>
- <span data-ttu-id="14889-158">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="14889-158">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="14889-159">Microsoft Defender per identità</span><span class="sxs-lookup"><span data-stu-id="14889-159">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="14889-160">Microsoft Defender per Office</span><span class="sxs-lookup"><span data-stu-id="14889-160">Microsoft Defender for Office</span></span>
- <span data-ttu-id="14889-161">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="14889-161">Skype for Business</span></span>

<span data-ttu-id="14889-162">**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**</span><span class="sxs-lookup"><span data-stu-id="14889-162">**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**</span></span><br>
<span data-ttu-id="14889-163">Con Microsoft 365 Defender, Defender for Endpoint e varie soluzioni di sicurezza Microsoft formano una famiglia di prodotti di difesa aziendale unificata pre e post-violazione che si integra in modo nativo tra endpoint, identità, posta elettronica e applicazioni per rilevare, prevenire, analizzare e rispondere automaticamente ad attacchi sofisticati.</span><span class="sxs-lookup"><span data-stu-id="14889-163">With Microsoft 365 Defender, Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate, and automatically respond to sophisticated attacks.</span></span>


## <a name="related-topic"></a><span data-ttu-id="14889-164">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="14889-164">Related topic</span></span>
[<span data-ttu-id="14889-165">Microsoft Defender for Endpoint consente di rilevare minacce sofisticate</span><span class="sxs-lookup"><span data-stu-id="14889-165">Microsoft Defender for Endpoint helps detect sophisticated threats</span></span>](https://www.microsoft.com/itshowcase/microsoft-defender-atps-antivirus-capabilities-boost-malware-protection)
