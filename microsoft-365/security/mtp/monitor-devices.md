---
title: Report di monitoraggio & dispositivi - Centro sicurezza
description: Descrive come mantenere i dispositivi sicuri, aggiornati e individuare potenziali minacce nell'organizzazione
keywords: sicurezza, malware, Microsoft 365, M365, centro sicurezza, monitorare, report, dispositivi
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: b9580f904f9cc5043fa3e825007339ce66daaa72
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930499"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="fd3e4-104">Monitoraggio e creazione di report dei dispositivi nel Centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fd3e4-104">Device monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fd3e4-105">Mantenere i dispositivi sicuri, aggiornati e individuare potenziali minacce nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-105">Keep your devices secure, up-to-date, and spot potential threats in the Microsoft 365 security center.</span></span>

## <a name="view-device-alerts"></a><span data-ttu-id="fd3e4-106">Visualizzare gli avvisi per i dispositivi</span><span class="sxs-lookup"><span data-stu-id="fd3e4-106">View device alerts</span></span>

<span data-ttu-id="fd3e4-107">Ricevere avvisi aggiornati sull'attività di violazione e altre minacce nei dispositivi da Microsoft Defender per Endpoint (disponibile con una licenza E5).</span><span class="sxs-lookup"><span data-stu-id="fd3e4-107">Get up-to-date alerts about breach activity and other threats on your devices from Microsoft Defender for Endpoint (available with an E5 license).</span></span> <span data-ttu-id="fd3e4-108">Il Centro sicurezza Microsoft 365 monitora in modo efficace questi avvisi a un livello elevato usando il flusso di lavoro preferito.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-108">Microsoft 365 security center effectively monitors these alerts at a high level using your preferred workflow.</span></span>

### <a name="monitor-high-impact-alerts"></a><span data-ttu-id="fd3e4-109">Monitorare gli avvisi ad alto impatto</span><span class="sxs-lookup"><span data-stu-id="fd3e4-109">Monitor high-impact alerts</span></span>

<span data-ttu-id="fd3e4-110">Ogni avviso di Microsoft Defender per endpoint ha una gravità corrispondente (alta, media, bassa o informativo).</span><span class="sxs-lookup"><span data-stu-id="fd3e4-110">Each Microsoft Defender for Endpoint alert has a corresponding severity (high, medium, low, or informational).</span></span> <span data-ttu-id="fd3e4-111">Indica un potenziale impatto sulla rete se lasciato automatico.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-111">It indicates potential impact to your network if left unattended.</span></span>  

<span data-ttu-id="fd3e4-112">Usa la **scheda Gravità avviso dispositivo** per concentrarti in modo specifico sugli avvisi più gravi e che potrebbero richiedere una risposta immediata.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-112">Use the **Device alert severity** card to focus specifically on alerts that are more severe and might require immediate response.</span></span> <span data-ttu-id="fd3e4-113">Da questa scheda puoi visualizzare altre informazioni nel portale di Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-113">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![Scheda di gravità degli avvisi del dispositivo](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a><span data-ttu-id="fd3e4-115">Comprendere le origini degli avvisi</span><span class="sxs-lookup"><span data-stu-id="fd3e4-115">Understand sources of alerts</span></span>

<span data-ttu-id="fd3e4-116">Microsoft Defender for Endpoint sfrutta i dati di un'ampia gamma di sensori di sicurezza e origini di intelligence per generare avvisi.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-116">Microsoft Defender for Endpoint leverages data from a broad range of security sensors and intelligence sources to generate alerts.</span></span> <span data-ttu-id="fd3e4-117">Ad esempio, può usare le informazioni di rilevamento di Microsoft Defender Antivirus e antimalware di terze parti.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-117">For example, it can use detection information from Microsoft Defender Antivirus and third-party antimalware.</span></span> <span data-ttu-id="fd3e4-118">Può anche usare intelligence personalizzata per le minacce fornita tramite l'API del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-118">It can also use your own custom threat intelligence provided through the web service API.</span></span>

<span data-ttu-id="fd3e4-119">La **scheda delle origini di rilevamento degli** avvisi del dispositivo mostra la distribuzione degli avvisi in base all'origine.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-119">The **Device alert detection** sources card shows the distribution of alerts by source.</span></span> <span data-ttu-id="fd3e4-120">Tenere traccia delle attività correlate a determinate origini, in particolare alle origini personalizzate.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-120">Track activity related to certain sources, particularly your custom sources.</span></span> <span data-ttu-id="fd3e4-121">Puoi anche usare la scheda per concentrarti sugli avvisi provenienti da sensori non configurati per bloccare automaticamente attività dannose o componenti.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-121">You can also use the card to focus on alerts coming from sensors that aren't configured to automatically block malicious activity or components.</span></span>

![Scheda delle origini di rilevamento degli avvisi del dispositivo](../../media/device-alert-detection-sources.png)

<span data-ttu-id="fd3e4-123">Da questa scheda puoi visualizzare altre informazioni nel portale di Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-123">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a><span data-ttu-id="fd3e4-124">Comprendere i tipi di minacce che attivano gli avvisi</span><span class="sxs-lookup"><span data-stu-id="fd3e4-124">Understand the types of threats that trigger alerts</span></span>

<span data-ttu-id="fd3e4-125">Microsoft Defender per endpoint ordina ogni avviso in una categoria che rappresenta una determinata fase della catena di attacchi o del tipo di componente di minaccia.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-125">Microsoft Defender for Endpoint sorts each alert into a category representing a certain stage in the attack chain or type of threat component.</span></span> <span data-ttu-id="fd3e4-126">Ad esempio, un'attività di minaccia rilevata potrebbe essere classificata come "movimento laterale" per indicare che si è tentato di raggiungere altri dispositivi nella rete.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-126">For example, a detected threat activity might be categorized as "lateral movement" to indicate there was an attempt to reach other devices on the network.</span></span> <span data-ttu-id="fd3e4-127">È probabile che l'attività si sia verificata dopo che gli utenti malintenzionati hanno acquisito una posizione iniziale.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-127">The activity has likely occurred after attackers gained an initial foothold.</span></span> <span data-ttu-id="fd3e4-128">Quando viene rilevato, un componente di minaccia può essere classificato su larga come malware o in modo specifico come tipo di minaccia specifico.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-128">When detected, a threat component might be classified broadly as malware or specifically as a specific threat type.</span></span> <span data-ttu-id="fd3e4-129">Le specifiche includono ransomware, furto di credenziali o altri tipi di software dannoso o indesiderato.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-129">Specifics include ransomware, credential stealing, or other types of malicious or unwanted software.</span></span>

<span data-ttu-id="fd3e4-130">La **scheda categorie di minacce dispositivo** mostra la distribuzione degli avvisi in queste categorie.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-130">The **Device threat categories** card shows the distribution of alerts into these categories.</span></span> <span data-ttu-id="fd3e4-131">Utilizzare queste informazioni per identificare le attività relative alle minacce, ad esempio i tentativi di furto di credenziali, che in genere hanno un impatto maggiore rispetto ai tentativi di ingegneria sociale.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-131">Use this information to identify threat activity, such as credential theft attempts, that usually have higher impact than social engineering attempts.</span></span> <span data-ttu-id="fd3e4-132">Puoi anche monitorare le minacce potenzialmente distruttive come il ransomware.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-132">You can also to monitor for potentially destructive threats like ransomware.</span></span>

![Scheda categorie di minacce dispositivo](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a><span data-ttu-id="fd3e4-134">Monitorare gli avvisi attivi</span><span class="sxs-lookup"><span data-stu-id="fd3e4-134">Monitor active alerts</span></span>

<span data-ttu-id="fd3e4-135">La **scheda di stato dell'avviso** del dispositivo indica il numero di avvisi che non sono stati risolti e potrebbero richiedere attenzione.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-135">The **Device alert status** card indicates the number of alerts that haven't been resolved and may require attention.</span></span> <span data-ttu-id="fd3e4-136">Da questa scheda puoi visualizzare altre informazioni nel portale di Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-136">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![Scheda stato avviso dispositivo](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a><span data-ttu-id="fd3e4-138">Monitorare la classificazione degli avvisi risolti</span><span class="sxs-lookup"><span data-stu-id="fd3e4-138">Monitor classification of resolved alerts</span></span>

<span data-ttu-id="fd3e4-139">Durante la risoluzione di un avviso di Microsoft Defender per endpoint, il personale di sicurezza può specificare se un avviso è stato verificato come:</span><span class="sxs-lookup"><span data-stu-id="fd3e4-139">When resolving a Microsoft Defender for Endpoint alert, your security staff can specify whether an alert has been verified as:</span></span>

* <span data-ttu-id="fd3e4-140">Un vero avviso che identifica l'attività effettiva di violazione o i componenti delle minacce</span><span class="sxs-lookup"><span data-stu-id="fd3e4-140">A true alert that identifies actual breach activity or threat components</span></span>
* <span data-ttu-id="fd3e4-141">Un falso avviso che ha rilevato in modo errato attività normale</span><span class="sxs-lookup"><span data-stu-id="fd3e4-141">A false alert that has incorrectly detected normal activity</span></span>

<span data-ttu-id="fd3e4-142">La **scheda di classificazione degli avvisi** del dispositivo mostra se gli avvisi risolti sono stati classificati come avvisi veri o falsi.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-142">The **Device alert classification** card shows whether your resolved alerts have been classified as true or false alerts.</span></span> <span data-ttu-id="fd3e4-143">Da questa scheda puoi visualizzare altre informazioni nel portale di Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-143">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="fd3e4-144">Nota: in alcuni casi, le informazioni di classificazione non sono disponibili per determinati avvisi.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-144">Note: In some cases, classification information is unavailable for certain alerts.</span></span>

![Scheda di classificazione degli avvisi del dispositivo](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a><span data-ttu-id="fd3e4-146">Monitorare la determinazione degli avvisi risolti</span><span class="sxs-lookup"><span data-stu-id="fd3e4-146">Monitor determination of resolved alerts</span></span>

<span data-ttu-id="fd3e4-147">Oltre a classificare se un avviso è vero o falso durante la risoluzione, il personale di sicurezza può fornire una determinazione.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-147">Along with classifying whether an alert is true or false during resolution, your security staff can provide a determination.</span></span> <span data-ttu-id="fd3e4-148">Una determinazione indica il tipo di attività normale o dannosa trovata durante la convalida dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-148">A determination indicates the type of normal or malicious activity that was found while validating the alert.</span></span>

<span data-ttu-id="fd3e4-149">La **scheda di determinazione dell'avviso** del dispositivo mostra la determinazione fornita per ogni avviso.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-149">The **Device alert determination** card shows the determination provided for each alert.</span></span>

* <span data-ttu-id="fd3e4-150">**APT:** minaccia persistente avanzata, che indica che l'attività rilevata o il componente della minaccia fa parte di una violazione sofisticata progettata per ottenere una base nella rete interessata</span><span class="sxs-lookup"><span data-stu-id="fd3e4-150">**APT**: advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span></span>  
* <span data-ttu-id="fd3e4-151">**Malware:** file o codice dannoso</span><span class="sxs-lookup"><span data-stu-id="fd3e4-151">**Malware**: malicious file or code</span></span>
* <span data-ttu-id="fd3e4-152">**Personale di sicurezza:** normale attività eseguita dal personale di sicurezza</span><span class="sxs-lookup"><span data-stu-id="fd3e4-152">**Security personnel**: normal activity performed by security staff</span></span>
* <span data-ttu-id="fd3e4-153">**Test di sicurezza:** attività o componenti progettati per simulare minacce effettive e che dovrebbero attivare sensori di sicurezza e generare avvisi</span><span class="sxs-lookup"><span data-stu-id="fd3e4-153">**Security testing**: activity or components designed to simulate actual threats and expected to trigger security sensors and generate alerts</span></span>
* <span data-ttu-id="fd3e4-154">**Software indesiderato:** app e altri software non considerati dannosi, ma che violano in altro modo i criteri o gli standard di utilizzo accettabili</span><span class="sxs-lookup"><span data-stu-id="fd3e4-154">**Unwanted software**: apps and other software that are not considered malicious, but otherwise violate policy or acceptable use standards</span></span>
* <span data-ttu-id="fd3e4-155">**Altri**: qualsiasi altra determinazione che non rientra nei tipi forniti</span><span class="sxs-lookup"><span data-stu-id="fd3e4-155">**Others**: any other determination that doesn't fall under the provided types</span></span>

<span data-ttu-id="fd3e4-156">Da questa scheda puoi visualizzare altre informazioni in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-156">From this card, you can view more information in Microsoft Defender Security Center.</span></span>

![Scheda per la determinazione dell'avviso del dispositivo](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a><span data-ttu-id="fd3e4-158">Comprendere quali dispositivi sono a rischio</span><span class="sxs-lookup"><span data-stu-id="fd3e4-158">Understand which devices are at risk</span></span>

<span data-ttu-id="fd3e4-159">**La protezione dei** dispositivi mostra il livello di rischio per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-159">**Device protection** shows the risk level for devices.</span></span> <span data-ttu-id="fd3e4-160">Il livello di rischio si basa su fattori quali il tipo e la gravità degli avvisi nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-160">The risk level is based on factors such as the type and severity of alerts on the device.</span></span>

![Scheda di protezione del dispositivo](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a><span data-ttu-id="fd3e4-162">Monitorare e segnalare lo stato dei dispositivi gestiti da Intune</span><span class="sxs-lookup"><span data-stu-id="fd3e4-162">Monitor and report status of Intune-managed devices</span></span>

<span data-ttu-id="fd3e4-163">I report seguenti contengono i dati dei dispositivi registrati in Intune.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-163">The following reports contain data from devices enrolled in Intune.</span></span> <span data-ttu-id="fd3e4-164">I dati dei dispositivi non sono inclusi.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-164">Data from unenrolled devices isn't included.</span></span> <span data-ttu-id="fd3e4-165">Solo gli amministratori globali possono visualizzare queste schede.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-165">Only Global Administrators can view these cards.</span></span>

<span data-ttu-id="fd3e4-166">I dati dei dispositivi registrati in Intune includono:</span><span class="sxs-lookup"><span data-stu-id="fd3e4-166">Intune enrolled device data includes:</span></span>

* <span data-ttu-id="fd3e4-167">Conformità dispositivo</span><span class="sxs-lookup"><span data-stu-id="fd3e4-167">Device compliance</span></span>
* <span data-ttu-id="fd3e4-168">Dispositivi con malware attivo</span><span class="sxs-lookup"><span data-stu-id="fd3e4-168">Devices with active malware</span></span>
* <span data-ttu-id="fd3e4-169">Tipi di malware nei dispositivi</span><span class="sxs-lookup"><span data-stu-id="fd3e4-169">Types of malware on devices</span></span>
* <span data-ttu-id="fd3e4-170">Malware nei dispositivi</span><span class="sxs-lookup"><span data-stu-id="fd3e4-170">Malware on devices</span></span>
* <span data-ttu-id="fd3e4-171">Dispositivi con rilevamenti di malware</span><span class="sxs-lookup"><span data-stu-id="fd3e4-171">Devices with malware detections</span></span>
* <span data-ttu-id="fd3e4-172">Utenti con rilevamenti di malware</span><span class="sxs-lookup"><span data-stu-id="fd3e4-172">Users with malware detections</span></span>

### <a name="monitor-device-compliance"></a><span data-ttu-id="fd3e4-173">Monitorare la conformità dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="fd3e4-173">Monitor device compliance</span></span>

<span data-ttu-id="fd3e4-174">**La conformità dei** dispositivi mostra quanti dispositivi sono registrati in Intune sono conformi ai criteri di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-174">**Device compliance** shows how many devices that are enrolled in Intune comply with configuration policies.</span></span>

![Scheda di conformità del dispositivo](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a><span data-ttu-id="fd3e4-176">Individuare i dispositivi con rilevamenti di malware</span><span class="sxs-lookup"><span data-stu-id="fd3e4-176">Discover devices with malware detections</span></span>

<span data-ttu-id="fd3e4-177">**I rilevamenti di malware dei** dispositivi forniscono il numero di dispositivi registrati a Intune con malware che non è stato risolto completamente.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-177">**Device malware detections** provide the number of Intune enrolled devices with malware that hasn't been fully resolved.</span></span> <span data-ttu-id="fd3e4-178">La mancanza di risoluzione può essere causata da azioni in sospeso, un riavvio, un'analisi completa, azioni manuali dell'utente o se l'azione di correzione non è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-178">A lack of resolution can be because of pending actions, a restart, a full scan, manual user actions, or if the remediation action was not successfully completed.</span></span>

![Scheda rilevamenti malware dei dispositivi](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a><span data-ttu-id="fd3e4-180">Comprendere i tipi di malware rilevato</span><span class="sxs-lookup"><span data-stu-id="fd3e4-180">Understand the types of malware detected</span></span>

<span data-ttu-id="fd3e4-181">**I tipi di malware nei dispositivi** mostrano diversi tipi di malware rilevati nei dispositivi registrati in Intune.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-181">**Types of malware on devices** show different kinds of malware that have been detected on devices enrolled in Intune.</span></span> <span data-ttu-id="fd3e4-182">È possibile analizzare ogni tipo nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-182">You can investigate each type in the Microsoft 365 security center.</span></span>

![Tipi di malware nella scheda dei dispositivi](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a><span data-ttu-id="fd3e4-184">Comprendere il malware specifico rilevato nei dispositivi</span><span class="sxs-lookup"><span data-stu-id="fd3e4-184">Understand the specific malware detected on your devices</span></span>

<span data-ttu-id="fd3e4-185">**Il malware nei dispositivi** fornisce un elenco del malware specifico rilevato nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-185">**Malware on devices** provides a list of the specific malware detected on your devices.</span></span>

![Scheda Malware nei dispositivi](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a><span data-ttu-id="fd3e4-187">Comprendere quali dispositivi hanno il maggior numero di malware</span><span class="sxs-lookup"><span data-stu-id="fd3e4-187">Understand which devices have the most malware</span></span>

<span data-ttu-id="fd3e4-188">**I dispositivi con rilevamenti di malware** mostrano quali dispositivi hanno il maggior numero di rilevamenti di malware.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-188">**Devices with malware detections** show which devices have the most malware detections.</span></span> <span data-ttu-id="fd3e4-189">nel Centro sicurezza Microsoft 365, è possibile verificare se il malware è attivo, chi usa il dispositivo e il relativo stato di gestione in Intune.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-189">in the Microsoft 365 security center, you can investigate whether malware is active, who uses the device, and its management status in Intune.</span></span>

![Scheda dispositivi con rilevamento malware](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a><span data-ttu-id="fd3e4-191">Comprendere quali utenti dispongono di dispositivi con il maggior numero di malware</span><span class="sxs-lookup"><span data-stu-id="fd3e4-191">Understand which users have devices with the most malware</span></span>

<span data-ttu-id="fd3e4-192">**Gli utenti con rilevamenti di malware** mostrano gli utenti con dispositivi con il maggior numero di rilevamenti di malware.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-192">**Users with malware detections** show users with devices that had the most malware detections.</span></span> <span data-ttu-id="fd3e4-193">Nel Centro sicurezza Microsoft 365 è possibile vedere quanti dispositivi sono assegnati a ogni utente e ulteriori informazioni su ogni dispositivo e sul tipo di malware.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-193">In the Microsoft 365 security center, you can see how many devices are assigned to each user and more information about each device and the type of malware.</span></span>

![Utenti con scheda di rilevamento malware](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-attack-surface-reduction-rule-deployment-and-detections"></a><span data-ttu-id="fd3e4-195">Monitorare e gestire la distribuzione e i rilevamenti delle regole per la riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="fd3e4-195">Monitor and manage attack surface reduction rule deployment and detections</span></span>

<span data-ttu-id="fd3e4-196">Le regole di riduzione della superficie di attacco [(ASR, Attack Surface Reduction)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) consentono di impedire azioni e app che in genere vengono usate dal malware per la ricerca di exploit per infettare i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-196">[Attack Surface Reduction (ASR) rules](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) help prevent actions and apps that are typically used by exploit-seeking malware to infect devices.</span></span> <span data-ttu-id="fd3e4-197">Queste regole controllano il modo in cui possono essere eseguiti i file eseguibili.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-197">These rules control when and how executables can run.</span></span> <span data-ttu-id="fd3e4-198">Ad esempio, è possibile impedire a JavaScript o VBScript di avviare un file eseguibile scaricato, bloccare le chiamate API Win32 dalle macro di Office o bloccare i processi eseguiti da unità USB.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-198">For example, you can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, or block processes that run from USB drives.</span></span>

![Scheda riduzione della superficie di attacco](../../media/attack-surface-reduction-rules.png)

<span data-ttu-id="fd3e4-200">La scheda **Regole per la riduzione della superficie di attacco** fornisce una panoramica della distribuzione delle regole in tutti i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-200">The **Attack surface reduction rules** card provides an overview of the deployment of rules across your devices.</span></span>

<span data-ttu-id="fd3e4-201">La barra superiore della scheda mostra il numero totale di dispositivi che si trovano nelle modalità di distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd3e4-201">The top bar on the card shows the total number of devices that are in the following deployment modes:</span></span>

* <span data-ttu-id="fd3e4-202">**Modalità di blocco:** dispositivi con almeno una regola configurata per bloccare l'attività rilevata</span><span class="sxs-lookup"><span data-stu-id="fd3e4-202">**Block mode**: devices with at least one rule configured to block detected activity</span></span>
* <span data-ttu-id="fd3e4-203">**Modalità di controllo:** dispositivi senza regole impostate per bloccare l'attività rilevata, ma con almeno una regola impostata per controllare l'attività rilevata</span><span class="sxs-lookup"><span data-stu-id="fd3e4-203">**Audit mode**: devices with no rules set to block detected activity, but has at least one rule set to audit detected activity</span></span>  
* <span data-ttu-id="fd3e4-204">**Disattivato:** dispositivi con tutte le regole asR disattivate</span><span class="sxs-lookup"><span data-stu-id="fd3e4-204">**Off**: devices with all ASR rules turned off</span></span>

<span data-ttu-id="fd3e4-205">La parte inferiore della scheda mostra le impostazioni per ciascuna regola in tutti i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-205">The lower part of this card shows settings by rule across your devices.</span></span> <span data-ttu-id="fd3e4-206">Ogni barra indica il numero di dispositivi impostati per bloccare, controllare il rilevamento o disattivare completamente la regola.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-206">Each bar indicates the number of devices that are set to block, audit detection, or have the rule completely turned off.</span></span>

### <a name="view-asr-detections"></a><span data-ttu-id="fd3e4-207">Visualizzare i rilevamenti asr</span><span class="sxs-lookup"><span data-stu-id="fd3e4-207">View ASR detections</span></span>

<span data-ttu-id="fd3e4-208">Per visualizzare informazioni dettagliate sui rilevamenti delle  regole asr nella rete, selezionare Visualizza rilevamenti nella scheda delle regole di riduzione **della superficie di** attacco.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-208">To view detailed information about ASR rule detections in your network, select **View detections** on the **Attack surface reduction rules** card.</span></span> <span data-ttu-id="fd3e4-209">Verrà **visualizzata la** scheda Rilevamenti nella pagina dettagliata del report.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-209">The **Detections** tab in the detailed report page will open.</span></span>

![Scheda Rilevamenti](../../media/detections-tab.png)

<span data-ttu-id="fd3e4-211">Il grafico nella parte superiore della pagina mostra i rilevamenti nel corso del tempo di sovrapposizione dei rilevamenti bloccati o controllati.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-211">The chart at the top of the page shows detections over time stacking detections that were either blocked or audited.</span></span> <span data-ttu-id="fd3e4-212">La tabella in basso elenca i rilevamenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-212">The table at the bottom lists the most recent detections.</span></span> <span data-ttu-id="fd3e4-213">Utilizzare le informazioni seguenti nella tabella per comprendere la natura dei rilevamenti:</span><span class="sxs-lookup"><span data-stu-id="fd3e4-213">Use the following information on the table to understand the nature of the detections:</span></span>

* <span data-ttu-id="fd3e4-214">**File rilevato:** il file, in genere uno script o un documento, il cui contenuto ha attivato l'attività di attacco sospetto</span><span class="sxs-lookup"><span data-stu-id="fd3e4-214">**Detected file**: the file, typically a script or document, whose contents triggered the suspected attack activity</span></span>
* <span data-ttu-id="fd3e4-215">**Regola**: nome che descrive le attività di attacco che la regola è progettata per intercettare.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-215">**Rule**: name describing the attack activities the rule is designed to catch.</span></span> <span data-ttu-id="fd3e4-216">Informazioni sulle regole ASR esistenti</span><span class="sxs-lookup"><span data-stu-id="fd3e4-216">Read about existing ASR rules</span></span>
* <span data-ttu-id="fd3e4-217">**App di origine:** l'applicazione che ha caricato o eseguito il contenuto che attiva l'attività di attacco sospetto.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-217">**Source app**: the application that loaded or executed content triggering the suspected attack activity.</span></span> <span data-ttu-id="fd3e4-218">Potrebbe trattarsi di un'applicazione legittima, ad esempio un Web browser, un'applicazione di Office o uno strumento di sistema come PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd3e4-218">It could be a legitimate application, such as web browser, an Office application, or a system tool like PowerShell</span></span>
* <span data-ttu-id="fd3e4-219">**Autore:** il fornitore che ha rilasciato l'app di origine</span><span class="sxs-lookup"><span data-stu-id="fd3e4-219">**Publisher**: the vendor that released the source app</span></span>

### <a name="review-device-asr-rule-settings"></a><span data-ttu-id="fd3e4-220">Esaminare le impostazioni delle regole di registrazione asr del dispositivo</span><span class="sxs-lookup"><span data-stu-id="fd3e4-220">Review device ASR rule settings</span></span>

<span data-ttu-id="fd3e4-221">Nella pagina **del report Sulle regole di riduzione della superficie** di attacco passare alla scheda **Configurazione** per esaminare le impostazioni delle regole per i singoli dispositivi.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-221">In the **Attack surface reduction rules** report page, go to the **Configuration** tab to review rule settings for individual devices.</span></span> <span data-ttu-id="fd3e4-222">Seleziona un dispositivo per ottenere informazioni dettagliate sul fatto che ogni regola sia in modalità di blocco, in modalità di controllo o completamente disattivata.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-222">Select a device to get detailed information about whether each rule is in block mode, audit mode, or turned off entirely.</span></span>

![Scheda Configuration](../../media/configuration-tab.png)

<span data-ttu-id="fd3e4-224">Microsoft Intune offre funzionalità di gestione per le regole ASR.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-224">Microsoft Intune provides management functionality for your ASR rules.</span></span> <span data-ttu-id="fd3e4-225">Se si desidera aggiornare le impostazioni, **selezionare** Introduzione in **Configura** dispositivi nella scheda per aprire la gestione dei dispositivi in Intune.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-225">If you want to update your settings, select **Get started** under **Configure devices** in the tab to open device management on Intune.</span></span>

### <a name="exclude-files-from-asr-rules"></a><span data-ttu-id="fd3e4-226">Escludere i file dalle regole asr</span><span class="sxs-lookup"><span data-stu-id="fd3e4-226">Exclude files from ASR rules</span></span>

<span data-ttu-id="fd3e4-227">Il Centro sicurezza Microsoft 365 [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) raccoglie i nomi dei file che potrebbe essere necessario escludere dai rilevamenti dalle regole di riduzione della superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-227">Microsoft 365 security center collects the names of the [files you might want to exclude](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) from detections by attack surface reduction rules.</span></span> <span data-ttu-id="fd3e4-228">Escludendo i file, è possibile ridurre i rilevamenti di falsi positivi e distribuire in modo più sicuro le regole di riduzione della superficie di attacco in modalità blocco.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-228">By excluding files, you can reduce false positive detections and more confidently deploy attack surface reduction rules in block mode.</span></span>

<span data-ttu-id="fd3e4-229">Le esclusioni sono gestite in Microsoft Intune, ma il Centro sicurezza Microsoft 365 offre uno strumento di analisi che consente di comprendere i file.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-229">The exclusions are managed on Microsoft Intune, but Microsoft 365 security center provides an analysis tool to help you understand the files.</span></span> <span data-ttu-id="fd3e4-230">Per iniziare a raccogliere i file per l'esclusione, vai alla **scheda** Aggiungi esclusioni nella pagina del report sulle regole di **riduzione della superficie** di attacco.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-230">To start collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.</span></span>

>[!NOTE]  
><span data-ttu-id="fd3e4-231">Lo strumento analizza i rilevamenti in base a tutte le regole di riduzione della superficie di attacco, ma [solo alcune regole supportano le esclusioni.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr)</span><span class="sxs-lookup"><span data-stu-id="fd3e4-231">The tool analyzes detections by all attack surface reduction rules, but [only some rules support exclusions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr).</span></span>

![Scheda Aggiungi esclusioni](../../media/add-exclusions-tab.png)

<span data-ttu-id="fd3e4-233">Nella tabella sono elencati tutti i nomi di file rilevati dalle regole di riduzione della superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-233">The table lists all the file names detected by your attack surface reduction rules.</span></span> <span data-ttu-id="fd3e4-234">È possibile selezionare i file per esaminare l'impatto dell'esclusione:</span><span class="sxs-lookup"><span data-stu-id="fd3e4-234">You can select files to review the impact of excluding them:</span></span>

* <span data-ttu-id="fd3e4-235">Numero di rilevamenti in meno</span><span class="sxs-lookup"><span data-stu-id="fd3e4-235">How many fewer detections</span></span>
* <span data-ttu-id="fd3e4-236">Numero di dispositivi in meno che segnalano i rilevamenti</span><span class="sxs-lookup"><span data-stu-id="fd3e4-236">How many fewer devices report the detections</span></span>

<span data-ttu-id="fd3e4-237">Per ottenere un elenco dei file selezionati con i relativi percorsi completi per l'esclusione, selezionare **Ottieni percorsi di esclusione.**</span><span class="sxs-lookup"><span data-stu-id="fd3e4-237">To get a list of the selected files with their full paths for exclusion, select **Get exclusion paths**.</span></span>

<span data-ttu-id="fd3e4-238">I log per la regola ASR bloccano il furto delle credenziali dal sottosistema dell'autorità di sicurezza locale **di Windows (lsass.exe)** acquisiscono l'app **di originelsass.exe**.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-238">Logs for the ASR rule **Block credential stealing from the Windows local security authority subsystem (lsass.exe)** capture the source app **lsass.exe**.</span></span> <span data-ttu-id="fd3e4-239">Si tratta di un normale file di sistema, ma acquisito come file rilevato.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-239">It is a normal system file, but captured as the detected file.</span></span> <span data-ttu-id="fd3e4-240">Di conseguenza, l'elenco generato di percorsi di esclusione includerà questo file.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-240">As a result, the generated list of exclusion paths will include this file.</span></span> <span data-ttu-id="fd3e4-241">Per escludere il file che ha attivato questa regola **anzichélsass.exe**, usa il percorso dell'app di origine anziché il file rilevato.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-241">To exclude the file that triggered this rule instead of **lsass.exe**, use the path to the source app instead of the detected file.</span></span>

<span data-ttu-id="fd3e4-242">Per individuare l'app di origine, eseguire la [query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) di ricerca avanzata seguente per questa regola specifica (identificata dall'ID regola 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span><span class="sxs-lookup"><span data-stu-id="fd3e4-242">To locate the source app, run the following [advanced hunting query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) for this specific rule (identified by rule ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a><span data-ttu-id="fd3e4-243">Controllare i file per l'esclusione</span><span class="sxs-lookup"><span data-stu-id="fd3e4-243">Check files for exclusion</span></span>

<span data-ttu-id="fd3e4-244">Prima di escludere un file da ASR, si consiglia di esaminare il file per determinare se non è effettivamente dannoso.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-244">Before excluding a file from ASR, we recommend that you inspect the file to determine if it's indeed not malicious.</span></span>

<span data-ttu-id="fd3e4-245">Per esaminare un file, usare la pagina [delle informazioni sul file](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-245">To review a file, use the [file information page](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) on Microsoft Defender Security Center.</span></span> <span data-ttu-id="fd3e4-246">La pagina fornisce informazioni sulla diffusione e il rapporto di rilevamento antivirus VirusTotal.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-246">The page provides prevalence information and the VirusTotal antivirus detection ratio.</span></span> <span data-ttu-id="fd3e4-247">È inoltre possibile utilizzare la pagina per inviare il file per l'analisi approfondita.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-247">You can also use the page to submit the file for deep analysis.</span></span>

<span data-ttu-id="fd3e4-248">Per individuare un file rilevato in Microsoft Defender Security Center, cercare tutti i rilevamenti ASR usando la query di ricerca avanzata seguente:</span><span class="sxs-lookup"><span data-stu-id="fd3e4-248">To locate a detected file in Microsoft Defender Security Center, search for all ASR detections using the following advanced hunting query:</span></span>

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

<span data-ttu-id="fd3e4-249">Usa **SHA1** o **InitiatingProcessSHA1** nei risultati per cercare il file usando la barra di ricerca universale in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="fd3e4-249">Use the **SHA1** or the **InitiatingProcessSHA1** in the results to search for the file using the universal search bar in Microsoft Defender Security Center.</span></span>
