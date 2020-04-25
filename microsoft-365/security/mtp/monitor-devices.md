---
title: Monitoraggio e Reporting dei dispositivi nel centro sicurezza Microsoft 365
description: Descrive in che modo è possibile mantenere i dispositivi sicuri, aggiornati e individuare potenziali minacce nell'organizzazione
keywords: sicurezza, malware, Microsoft 365, M365, Centro sicurezza, monitoraggio, report, dispositivi
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: f8adb04e968f19c6b0577127e4f9c0ceb7d9e315
ms.sourcegitcommit: 1e9ce51efa583c33625299d17e37f58048a4169c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "43804877"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="1e77a-104">Monitoraggio e Reporting dei dispositivi nel centro sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1e77a-104">Device monitoring and reporting in the Microsoft 365 security center</span></span>

<span data-ttu-id="1e77a-105">Mantenere i dispositivi sicuri, aggiornati e individuare potenziali minacce nel centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1e77a-105">Keep your devices secure, up-to-date, and spot potential threats in the Microsoft 365 security center.</span></span>

## <a name="view-device-alerts"></a><span data-ttu-id="1e77a-106">Visualizzare gli avvisi per i dispositivi</span><span class="sxs-lookup"><span data-stu-id="1e77a-106">View device alerts</span></span>

<span data-ttu-id="1e77a-107">Ottenere avvisi aggiornati sull'attività di violazione e altre minacce sui dispositivi da Microsoft Defender ATP (disponibile con una licenza E5).</span><span class="sxs-lookup"><span data-stu-id="1e77a-107">Get up-to-date alerts about breach activity and other threats on your devices from Microsoft Defender ATP (available with an E5 license).</span></span> <span data-ttu-id="1e77a-108">Microsoft 365 Security Center monitora efficacemente gli avvisi a un livello elevato utilizzando il flusso di lavoro preferito.</span><span class="sxs-lookup"><span data-stu-id="1e77a-108">Microsoft 365 security center effectively monitors these alerts at a high level using your preferred workflow.</span></span>

### <a name="monitor-high-impact-alerts"></a><span data-ttu-id="1e77a-109">Monitorare gli avvisi ad impatto elevato</span><span class="sxs-lookup"><span data-stu-id="1e77a-109">Monitor high-impact alerts</span></span>

<span data-ttu-id="1e77a-110">Ogni avviso del trifosfato di adenosina di Microsoft Defender ha un livello di gravità corrispondente (alto, medio, basso o informativo) che indica il suo impatto potenziale sulla rete se non è presente.</span><span class="sxs-lookup"><span data-stu-id="1e77a-110">Each Microsoft Defender ATP alert has a corresponding severity (high, medium, low, or informational) that indicates its potential impact to your network if left unattended.</span></span>  

<span data-ttu-id="1e77a-111">Utilizzare la scheda **gravità avviso dispositivo** per concentrarsi in modo specifico sugli avvisi più gravi e potrebbe richiedere una risposta immediata.</span><span class="sxs-lookup"><span data-stu-id="1e77a-111">Use the **Device alert severity** card to focus specifically on alerts that are more severe and might require immediate response.</span></span> <span data-ttu-id="1e77a-112">Da questa scheda, è possibile visualizzare altre informazioni sul portale Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="1e77a-112">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![Scheda di gravità avvisi dispositivo](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a><span data-ttu-id="1e77a-114">Informazioni sulle origini degli avvisi</span><span class="sxs-lookup"><span data-stu-id="1e77a-114">Understand sources of alerts</span></span>

<span data-ttu-id="1e77a-115">Microsoft Defender ATP utilizza i dati provenienti da una vasta gamma di sensori di sicurezza e fonti di intelligence per generare avvisi.</span><span class="sxs-lookup"><span data-stu-id="1e77a-115">Microsoft Defender ATP leverages data from a broad range of security sensors and intelligence sources to generate alerts.</span></span> <span data-ttu-id="1e77a-116">Ad esempio, è possibile utilizzare le informazioni di rilevamento di Windows Defender Antivirus e antimalware di terze parti, nonché la propria Intelligence di minacce personalizzata fornita tramite l'API del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="1e77a-116">For example, it can use detection information from Windows Defender Antivirus and third-party antimalware, as well as your own custom threat intelligence provided through the web service API.</span></span>

<span data-ttu-id="1e77a-117">La scheda fonti di **rilevamento avvisi dispositivo** Visualizza la distribuzione degli avvisi per origine.</span><span class="sxs-lookup"><span data-stu-id="1e77a-117">The **Device alert detection** sources card shows the distribution of alerts by source.</span></span> <span data-ttu-id="1e77a-118">Questa scheda può essere utile per monitorare le attività relative a determinate origini, in particolare le origini personalizzate.</span><span class="sxs-lookup"><span data-stu-id="1e77a-118">This card can help you track activity related to certain sources, particularly your custom sources.</span></span> <span data-ttu-id="1e77a-119">È inoltre possibile utilizzare questa pagina per concentrarsi sugli avvisi provenienti da sensori che non sono configurati per bloccare automaticamente le attività o i componenti dannosi.</span><span class="sxs-lookup"><span data-stu-id="1e77a-119">You can also use this to focus on alerts coming from sensors that are not configured to automatically block malicious activity or components.</span></span>

![Scheda fonti di rilevamento avvisi dispositivo](../../media/device-alert-detection-sources.png)

<span data-ttu-id="1e77a-121">Da questa scheda, è possibile visualizzare altre informazioni sul portale Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="1e77a-121">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a><span data-ttu-id="1e77a-122">Comprendere i tipi di minacce che attivano gli avvisi</span><span class="sxs-lookup"><span data-stu-id="1e77a-122">Understand the types of threats that trigger alerts</span></span>

<span data-ttu-id="1e77a-123">Microsoft Defender ATP Ordina ogni avviso in una categoria che rappresenta una determinata fase della catena di attacco o un tipo di componente di minaccia.</span><span class="sxs-lookup"><span data-stu-id="1e77a-123">Microsoft Defender ATP sorts each alert into a category representing a certain stage in the attack chain or a type of threat component.</span></span> <span data-ttu-id="1e77a-124">Ad esempio, un'attività di minacce rilevata potrebbe essere categorizzata come "movimento laterale" per indicare che si è verificato un tentativo di raggiungere altri dispositivi sulla rete.</span><span class="sxs-lookup"><span data-stu-id="1e77a-124">For example, a detected threat activity might be categorized as "lateral movement" to indicate that there was an attempt to reach other devices on the network.</span></span> <span data-ttu-id="1e77a-125">L'attività è probabile che si è verificato anche dopo che gli aggressori hanno acquisito un appiglio iniziale.</span><span class="sxs-lookup"><span data-stu-id="1e77a-125">The activity has also likely occurred after attackers gained an initial foothold.</span></span> <span data-ttu-id="1e77a-126">Una volta rilevato, un componente di minacce potrebbe essere classificato come malware, o più specificamente come ransomware, furto di credenziali o altri tipi di software dannoso o indesiderato.</span><span class="sxs-lookup"><span data-stu-id="1e77a-126">When detected, a threat component might either be classified broadly as malware, or more specifically as ransomware, credential stealing, or other types of malicious or unwanted software.</span></span>

<span data-ttu-id="1e77a-127">La scheda **categorie minacce dispositivo** Visualizza la distribuzione degli avvisi in queste categorie.</span><span class="sxs-lookup"><span data-stu-id="1e77a-127">The **Device threat categories** card shows the distribution of alerts into these categories.</span></span> <span data-ttu-id="1e77a-128">È possibile utilizzare queste informazioni per identificare le attività di minacce, ad esempio i tentativi di furto delle credenziali, che possono avere un impatto maggiore rispetto ai tentativi di social engineering.</span><span class="sxs-lookup"><span data-stu-id="1e77a-128">You can use this information to identify threat activity, such as credential theft attempts, that can have higher impact compared to social engineering attempts.</span></span> <span data-ttu-id="1e77a-129">È inoltre possibile utilizzare queste informazioni per eseguire il monitoraggio di minacce potenzialmente distruttive come ransomware.</span><span class="sxs-lookup"><span data-stu-id="1e77a-129">You can also use this information to monitor for potentially destructive threats like ransomware.</span></span>

![Scheda categorie di minacce per dispositivi](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a><span data-ttu-id="1e77a-131">Monitorare gli avvisi attivi</span><span class="sxs-lookup"><span data-stu-id="1e77a-131">Monitor active alerts</span></span>

<span data-ttu-id="1e77a-132">La scheda **stato avviso dispositivo** indica il numero di avvisi che non sono stati risolti e che potrebbero richiedere attenzione.</span><span class="sxs-lookup"><span data-stu-id="1e77a-132">The **Device alert status** card indicates the number of alerts that have not been resolved and might require attention.</span></span> <span data-ttu-id="1e77a-133">Da questa scheda, è possibile visualizzare altre informazioni sul portale Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="1e77a-133">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![Scheda stato avviso dispositivo](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a><span data-ttu-id="1e77a-135">Monitorare la classificazione degli avvisi risolti</span><span class="sxs-lookup"><span data-stu-id="1e77a-135">Monitor classification of resolved alerts</span></span>

<span data-ttu-id="1e77a-136">Durante la risoluzione di un avviso di Microsoft Defender ATP, il personale di sicurezza può specificare se un avviso è stato verificato come:</span><span class="sxs-lookup"><span data-stu-id="1e77a-136">When resolving a Microsoft Defender ATP alert, your security staff can specify whether an alert has been verified as:</span></span>

* <span data-ttu-id="1e77a-137">Un avviso vero che identifica le attività di violazione effettive o i componenti di minaccia</span><span class="sxs-lookup"><span data-stu-id="1e77a-137">A true alert that identifies actual breach activity or threat components</span></span>
* <span data-ttu-id="1e77a-138">Un falso avviso che ha rilevato erroneamente attività normale</span><span class="sxs-lookup"><span data-stu-id="1e77a-138">A false alert that has incorrectly detected normal activity</span></span>

<span data-ttu-id="1e77a-139">La scheda di **classificazione avviso dispositivo** indica se gli avvisi risolti sono stati classificati come avvisi veri o falsi.</span><span class="sxs-lookup"><span data-stu-id="1e77a-139">The **Device alert classification** card shows whether your resolved alerts have been classified as true or false alerts.</span></span> <span data-ttu-id="1e77a-140">Da questa scheda, è possibile visualizzare altre informazioni sul portale Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="1e77a-140">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="1e77a-141">Nota: in alcuni casi, le informazioni di classificazione non sono disponibili per determinati avvisi.</span><span class="sxs-lookup"><span data-stu-id="1e77a-141">Note: In some cases, classification information is unavailable for certain alerts.</span></span>

![Scheda di classificazione degli avvisi dei dispositivi](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a><span data-ttu-id="1e77a-143">Monitorare la determinazione degli avvisi risolti</span><span class="sxs-lookup"><span data-stu-id="1e77a-143">Monitor determination of resolved alerts</span></span>

<span data-ttu-id="1e77a-144">Oltre a classificare se un avviso è vero o falso durante la risoluzione, il personale della sicurezza può fornire una determinazione, indicando il tipo di attività normale o dannosa individuata durante la convalida dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="1e77a-144">In addition to classifying whether an alert is true or false during resolution, your security staff can provide a determination, indicating the type of normal or malicious activity that was found while validating the alert.</span></span>

<span data-ttu-id="1e77a-145">La scheda di **determinazione dell'avviso del dispositivo** Visualizza la determinazione fornita per ogni avviso.</span><span class="sxs-lookup"><span data-stu-id="1e77a-145">The **Device alert determination** card shows the determination provided for each alert.</span></span>

* <span data-ttu-id="1e77a-146">**Apt**: Advanced Persistent Threat, che indica che l'attività rilevata o il componente di minaccia è parte di una sofisticata violazione progettata per ottenere un punto di appoggio nella rete in questione</span><span class="sxs-lookup"><span data-stu-id="1e77a-146">**APT**: advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span></span>  
* <span data-ttu-id="1e77a-147">**Malware**: file o codice dannoso</span><span class="sxs-lookup"><span data-stu-id="1e77a-147">**Malware**: malicious file or code</span></span>
* <span data-ttu-id="1e77a-148">**Personale di sicurezza**: attività normale eseguita dal personale della sicurezza</span><span class="sxs-lookup"><span data-stu-id="1e77a-148">**Security personnel**: normal activity performed by security staff</span></span>
* <span data-ttu-id="1e77a-149">**Test di sicurezza**: attività o componenti studiati per simulare le minacce effettive e prevedere l'attivazione di sensori di sicurezza e generare avvisi</span><span class="sxs-lookup"><span data-stu-id="1e77a-149">**Security testing**: activity or components designed to simulate actual threats and expected to trigger security sensors and generate alerts</span></span>
* <span data-ttu-id="1e77a-150">**Software indesiderato**: app e altri software che non sono considerati dannosi, ma violano in altro modo i criteri o gli standard di utilizzo accettabili</span><span class="sxs-lookup"><span data-stu-id="1e77a-150">**Unwanted software**: apps and other software that are not considered malicious, but otherwise violate policy or acceptable use standards</span></span>
* <span data-ttu-id="1e77a-151">**Altri**: eventuali altre determinazioni che non rientrano nei tipi forniti</span><span class="sxs-lookup"><span data-stu-id="1e77a-151">**Others**: any other determination that does not fall under the provided types</span></span>

<span data-ttu-id="1e77a-152">Da questa scheda, è possibile visualizzare altre informazioni in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="1e77a-152">From this card, you can view more information in Microsoft Defender Security Center.</span></span>

![Scheda di determinazione dell'avviso del dispositivo](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a><span data-ttu-id="1e77a-154">Comprendere quali dispositivi sono a rischio</span><span class="sxs-lookup"><span data-stu-id="1e77a-154">Understand which devices are at risk</span></span>

<span data-ttu-id="1e77a-155">La **protezione del dispositivo** Visualizza il livello di rischio per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1e77a-155">**Device protection** shows the risk level for devices.</span></span> <span data-ttu-id="1e77a-156">Il livello di rischio si basa su fattori quali il tipo e la gravità degli avvisi nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1e77a-156">The risk level is based on factors such as the type and severity of alerts on the device.</span></span>

![Scheda di protezione del dispositivo](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a><span data-ttu-id="1e77a-158">Monitorare e segnalare lo stato dei dispositivi gestiti da Intune</span><span class="sxs-lookup"><span data-stu-id="1e77a-158">Monitor and report status of Intune-managed devices</span></span>

<span data-ttu-id="1e77a-159">Nei rapporti seguenti sono contenuti dati provenienti da dispositivi registrati in Intune.</span><span class="sxs-lookup"><span data-stu-id="1e77a-159">The following reports contain data from devices enrolled in Intune.</span></span> <span data-ttu-id="1e77a-160">I dati dei dispositivi non registrati non sono inclusi.</span><span class="sxs-lookup"><span data-stu-id="1e77a-160">Data from unenrolled devices is not included.</span></span> <span data-ttu-id="1e77a-161">Solo gli amministratori globali possono visualizzare queste schede.</span><span class="sxs-lookup"><span data-stu-id="1e77a-161">Only Global Administrators can view these cards.</span></span>

<span data-ttu-id="1e77a-162">I dati dei dispositivi registrati di Intune includono:</span><span class="sxs-lookup"><span data-stu-id="1e77a-162">Intune enrolled device data includes:</span></span>

* <span data-ttu-id="1e77a-163">Conformità dispositivo</span><span class="sxs-lookup"><span data-stu-id="1e77a-163">Device compliance</span></span>
* <span data-ttu-id="1e77a-164">Dispositivi con malware attivo</span><span class="sxs-lookup"><span data-stu-id="1e77a-164">Devices with active malware</span></span>
* <span data-ttu-id="1e77a-165">Tipi di malware nei dispositivi</span><span class="sxs-lookup"><span data-stu-id="1e77a-165">Types of malware on devices</span></span>
* <span data-ttu-id="1e77a-166">Malware nei dispositivi</span><span class="sxs-lookup"><span data-stu-id="1e77a-166">Malware on devices</span></span>
* <span data-ttu-id="1e77a-167">Dispositivi con rilevamenti di malware</span><span class="sxs-lookup"><span data-stu-id="1e77a-167">Devices with malware detections</span></span>
* <span data-ttu-id="1e77a-168">Utenti con rilevamenti di malware</span><span class="sxs-lookup"><span data-stu-id="1e77a-168">Users with malware detections</span></span>

### <a name="monitor-device-compliance"></a><span data-ttu-id="1e77a-169">Monitorare la conformità del dispositivo</span><span class="sxs-lookup"><span data-stu-id="1e77a-169">Monitor device compliance</span></span>

<span data-ttu-id="1e77a-170">La **conformità del dispositivo** indica il numero di dispositivi registrati in Intune conformi ai criteri di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1e77a-170">**Device compliance** shows how many devices that are enrolled in Intune comply with configuration policies.</span></span>

![Scheda conformità dispositivo](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a><span data-ttu-id="1e77a-172">Individuare i dispositivi con rilevamenti di malware</span><span class="sxs-lookup"><span data-stu-id="1e77a-172">Discover devices with malware detections</span></span>

<span data-ttu-id="1e77a-173">I **rilevamenti di malware** per i dispositivi forniscono il numero di dispositivi registrati di Intune con malware che non sono stati completamente risolti.</span><span class="sxs-lookup"><span data-stu-id="1e77a-173">**Device malware detections** provide the number of Intune enrolled devices with malware that have not been fully resolved.</span></span> <span data-ttu-id="1e77a-174">Questo può essere dovuto a azioni in sospeso, a un riavvio, a un'analisi completa, azioni utente manuali o se l'azione di correzione non è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="1e77a-174">This can be due to pending actions, a restart, a full scan, manual user actions, or if the remediation action did not complete successfully.</span></span>

![Scheda rilevamenti malware dispositivo](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a><span data-ttu-id="1e77a-176">Informazioni sui tipi di malware rilevati</span><span class="sxs-lookup"><span data-stu-id="1e77a-176">Understand the types of malware detected</span></span>

<span data-ttu-id="1e77a-177">I **tipi di malware nei dispositivi** mostrano diversi tipi di malware che sono stati rilevati nei dispositivi registrati in Intune.</span><span class="sxs-lookup"><span data-stu-id="1e77a-177">**Types of malware on devices** show different kinds of malware that have been detected on devices enrolled in Intune.</span></span> <span data-ttu-id="1e77a-178">È possibile esaminare ogni tipo nel centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1e77a-178">You can investigate each type in the Microsoft 365 security center.</span></span>

![Tipi di malware sulla scheda dispositivi](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a><span data-ttu-id="1e77a-180">Comprendere il malware specifico rilevato nei dispositivi</span><span class="sxs-lookup"><span data-stu-id="1e77a-180">Understand the specific malware detected on your devices</span></span>

<span data-ttu-id="1e77a-181">Il **malware nei dispositivi** fornisce un elenco di malware specifici rilevati nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1e77a-181">**Malware on devices** provide a list of the specific malware detected on your devices.</span></span>

![Scheda malware su dispositivi](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a><span data-ttu-id="1e77a-183">Informazioni sui dispositivi con la maggior parte dei malware</span><span class="sxs-lookup"><span data-stu-id="1e77a-183">Understand which devices have the most malware</span></span>

<span data-ttu-id="1e77a-184">I **dispositivi con rilevamenti di malware** mostrano quali dispositivi presentano la maggior parte dei rilevamenti di malware.</span><span class="sxs-lookup"><span data-stu-id="1e77a-184">**Devices with malware detections** show which devices have the most malware detections.</span></span> <span data-ttu-id="1e77a-185">nel centro sicurezza Microsoft 365, è possibile verificare se il malware è attivo, chi usa il dispositivo e lo stato di gestione in Intune.</span><span class="sxs-lookup"><span data-stu-id="1e77a-185">in the Microsoft 365 security center, you can investigate whether malware is active, who uses the device, and its management status in Intune.</span></span>

![Scheda dispositivi con rilevamento malware](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a><span data-ttu-id="1e77a-187">Comprendere quali utenti dispongono di dispositivi con la maggior parte dei malware</span><span class="sxs-lookup"><span data-stu-id="1e77a-187">Understand which users have devices with the most malware</span></span>

<span data-ttu-id="1e77a-188">**Gli utenti che dispongono di rilevamenti di malware** mostrano agli utenti i dispositivi con più rilevamenti di malware.</span><span class="sxs-lookup"><span data-stu-id="1e77a-188">**Users with malware detections** show users with devices that had the most malware detections.</span></span> <span data-ttu-id="1e77a-189">Nel centro sicurezza Microsoft 365, è possibile visualizzare il numero di dispositivi assegnati a ciascun utente e ulteriori informazioni su ogni dispositivo e sul tipo di malware.</span><span class="sxs-lookup"><span data-stu-id="1e77a-189">In the Microsoft 365 security center, you can see how many devices are assigned to each user and more information about each device and the type of malware.</span></span>

![Utenti con scheda di rilevamento antimalware](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-asr-rule-deployment-and-detections"></a><span data-ttu-id="1e77a-191">Monitorare e gestire la distribuzione e i rilevamenti delle regole ASR</span><span class="sxs-lookup"><span data-stu-id="1e77a-191">Monitor and manage ASR rule deployment and detections</span></span>

<span data-ttu-id="1e77a-192">[Le regole di riduzione dell'attacco superficiale (ASR, Attack Surface Reduction)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) consentono di prevenire azioni e app che in genere vengono utilizzate da malware in grado di sfruttare i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1e77a-192">[Attack Surface Reduction (ASR) rules](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) help prevent actions and apps that are typically used by exploit-seeking malware to infect devices.</span></span> <span data-ttu-id="1e77a-193">Queste regole controllano il modo in cui possono essere eseguiti i file eseguibili.</span><span class="sxs-lookup"><span data-stu-id="1e77a-193">These rules control when and how executables can run.</span></span> <span data-ttu-id="1e77a-194">Ad esempio, è possibile impedire a JavaScript o VBScript di avviare un file eseguibile scaricato, bloccare le chiamate API Win32 dalle macro di Office o bloccare i processi eseguiti da unità USB.</span><span class="sxs-lookup"><span data-stu-id="1e77a-194">For example, you can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, or block processes that run from USB drives.</span></span>

![Scheda riduzioni superficie attacco](../../media/attack-surface-reduction-rules.png)

<span data-ttu-id="1e77a-196">La scheda **Regole per la riduzione della superficie di attacco** fornisce una panoramica della distribuzione delle regole in tutti i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1e77a-196">The **Attack surface reduction rules** card provides an overview of the deployment of rules across your devices.</span></span>

<span data-ttu-id="1e77a-197">La barra superiore della scheda mostra il numero totale di dispositivi che si trovano nelle modalità di distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e77a-197">The top bar on the card shows the total number of devices that are in the following deployment modes:</span></span>

* <span data-ttu-id="1e77a-198">**Modalità di blocco**: dispositivi con almeno una regola configurata per bloccare l'attività rilevata</span><span class="sxs-lookup"><span data-stu-id="1e77a-198">**Block mode**: devices with at least one rule configured to block detected activity</span></span>
* <span data-ttu-id="1e77a-199">**Modalità di controllo**: i dispositivi con nessuna regola impostata per bloccare l'attività rilevata, ma hanno almeno un set di regole per il controllo dell'attività rilevata</span><span class="sxs-lookup"><span data-stu-id="1e77a-199">**Audit mode**: devices with no rules set to block detected activity, but has at least one rule set to audit detected activity</span></span>  
* <span data-ttu-id="1e77a-200">**Disattivato**: i dispositivi con tutte le regole di ASR sono disattivati</span><span class="sxs-lookup"><span data-stu-id="1e77a-200">**Off**: devices with all ASR rules turned off</span></span>

<span data-ttu-id="1e77a-201">La parte inferiore della scheda mostra le impostazioni per ciascuna regola in tutti i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1e77a-201">The lower part of this card shows settings by rule across your devices.</span></span> <span data-ttu-id="1e77a-202">Ogni barra indica il numero di dispositivi bloccati o da controllare oppure con la regola completamente disattivata.</span><span class="sxs-lookup"><span data-stu-id="1e77a-202">Each bar indicates the number of devices that are set to block or audit detection or have the rule completely turned off.</span></span>

### <a name="view-asr-detections"></a><span data-ttu-id="1e77a-203">Visualizzazione dei rilevamenti ASR</span><span class="sxs-lookup"><span data-stu-id="1e77a-203">View ASR detections</span></span>

<span data-ttu-id="1e77a-204">Per visualizzare informazioni dettagliate sui rilevamenti delle regole di ASR nella rete, selezionare **Visualizza rilevamenti** nella scheda **regole di riduzione della superficie di attacco** .</span><span class="sxs-lookup"><span data-stu-id="1e77a-204">To view detailed information about ASR rule detections in your network, select **View detections** on the **Attack surface reduction rules** card.</span></span> <span data-ttu-id="1e77a-205">Verrà aperta la scheda **rilevamenti** nella pagina rapporto dettagliato.</span><span class="sxs-lookup"><span data-stu-id="1e77a-205">The **Detections** tab in the detailed report page will open.</span></span>

![Scheda rilevamenti](../../media/detections-tab.png)

<span data-ttu-id="1e77a-207">Il grafico nella parte superiore della pagina Visualizza rilevamenti nel tempo di rilevamenti di sovrapposizione che sono stati bloccati o controllati.</span><span class="sxs-lookup"><span data-stu-id="1e77a-207">The chart at the top of the page shows detections over time stacking detections that were either blocked or audited.</span></span> <span data-ttu-id="1e77a-208">La tabella in basso elenca i rilevamenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="1e77a-208">The table at the bottom lists the most recent detections.</span></span> <span data-ttu-id="1e77a-209">Utilizzare le informazioni seguenti nella tabella per comprendere la natura dei rilevamenti:</span><span class="sxs-lookup"><span data-stu-id="1e77a-209">Use the following information on the table to understand the nature of the detections:</span></span>

* <span data-ttu-id="1e77a-210">**File rilevato**: il file, in genere uno script o un documento, il cui contenuto ha attivato l'attività di attacco sospetta</span><span class="sxs-lookup"><span data-stu-id="1e77a-210">**Detected file**: the file, typically a script or a document, whose contents triggered the suspected attack activity</span></span>
* <span data-ttu-id="1e77a-211">**Regola**: nome che descrive le attività di attacco la regola è progettata per essere intercettata.</span><span class="sxs-lookup"><span data-stu-id="1e77a-211">**Rule**: name describing the attack activities the rule is designed to catch.</span></span> <span data-ttu-id="1e77a-212">Leggere le regole ASR esistenti</span><span class="sxs-lookup"><span data-stu-id="1e77a-212">Read about existing ASR rules</span></span>
* <span data-ttu-id="1e77a-213">**App di origine**: l'applicazione che ha caricato o eseguito contenuto che attiva l'attività di attacco sospetta.</span><span class="sxs-lookup"><span data-stu-id="1e77a-213">**Source app**: the application that loaded or executed content triggering the suspected attack activity.</span></span> <span data-ttu-id="1e77a-214">Potrebbe trattarsi di un'applicazione legittima, ad esempio il Web browser, un'applicazione di Office o uno strumento di sistema come PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e77a-214">This could be a legitimate application, such as web browser, an Office application, or a system tool like PowerShell</span></span>
* <span data-ttu-id="1e77a-215">**Publisher**: il fornitore che ha rilasciato l'app di origine</span><span class="sxs-lookup"><span data-stu-id="1e77a-215">**Publisher**: the vendor that released the source app</span></span>

### <a name="review-device-asr-rule-settings"></a><span data-ttu-id="1e77a-216">Esaminare le impostazioni della regola di ASR del dispositivo</span><span class="sxs-lookup"><span data-stu-id="1e77a-216">Review device ASR rule settings</span></span>

<span data-ttu-id="1e77a-217">Nella pagina rapporto **regole di riduzione della superficie di attacco** passare alla scheda **configurazione** per esaminare le impostazioni delle regole per i singoli dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1e77a-217">In the **Attack surface reduction rules** report page, go to the **Configuration** tab to review rule settings for individual devices.</span></span> <span data-ttu-id="1e77a-218">Selezionare un dispositivo per ottenere informazioni dettagliate sul fatto che ogni regola sia in modalità di blocco, modalità di controllo o disattivata completamente.</span><span class="sxs-lookup"><span data-stu-id="1e77a-218">Select a device to get detailed information about whether each rule is in block mode, audit mode, or turned off entirely.</span></span>

![Scheda configurazione](../../media/configuration-tab.png)

<span data-ttu-id="1e77a-220">Microsoft Intune offre funzionalità di gestione per le regole di ASR.</span><span class="sxs-lookup"><span data-stu-id="1e77a-220">Microsoft Intune provides management functionality for your ASR rules.</span></span> <span data-ttu-id="1e77a-221">Se si desidera aggiornare le impostazioni, selezionare **Get Started** in **Configure Devices** nella scheda per aprire Gestione dispositivi su Intune.</span><span class="sxs-lookup"><span data-stu-id="1e77a-221">If you want to update your settings, select **Get started** under **Configure devices** in the tab to open device management on Intune.</span></span>

### <a name="exclude-files-from-asr-rules"></a><span data-ttu-id="1e77a-222">Escludi file dalle regole di ASR</span><span class="sxs-lookup"><span data-stu-id="1e77a-222">Exclude files from ASR rules</span></span>

<span data-ttu-id="1e77a-223">Microsoft 365 Security Center raccoglie i nomi dei [file che potrebbe essere necessario escludere](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) dai rilevamenti tramite le regole di riduzione della superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="1e77a-223">Microsoft 365 security center collects the names of the [files you might want to exclude](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) from detections by attack surface reduction rules.</span></span> <span data-ttu-id="1e77a-224">Escludendo i file, è possibile ridurre i rilevamenti falsi positivi e distribuire in modo più sicuro le regole di riduzione della superficie di attacco in modalità di blocco.</span><span class="sxs-lookup"><span data-stu-id="1e77a-224">By excluding files, you can reduce false positive detections and more confidently deploy attack surface reduction rules in block mode.</span></span>

<span data-ttu-id="1e77a-225">Le esclusioni sono gestite su Microsoft Intune, ma Microsoft 365 Security Center fornisce uno strumento di analisi per facilitare la comprensione dei file.</span><span class="sxs-lookup"><span data-stu-id="1e77a-225">The exclusions are managed on Microsoft Intune, but Microsoft 365 security center provides an analysis tool to help you understand the files.</span></span> <span data-ttu-id="1e77a-226">Per avviare la raccolta dei file per l'esclusione, passare alla scheda **Aggiungi esclusioni** nella pagina rapporto **regole di riduzione della superficie di attacco** .</span><span class="sxs-lookup"><span data-stu-id="1e77a-226">To start collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.</span></span>

>[!NOTE]  
><span data-ttu-id="1e77a-227">Lo strumento analizza i rilevamenti per tutte le regole di riduzione della superficie di attacco, ma [solo alcune regole supportano le esclusioni](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr).</span><span class="sxs-lookup"><span data-stu-id="1e77a-227">The tool analyzes detections by all attack surface reduction rules, but [only some rules support exclusions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr).</span></span>

![Scheda Aggiungi esclusioni](../../media/add-exclusions-tab.png)

<span data-ttu-id="1e77a-229">Nella tabella sono elencati tutti i nomi di file rilevati dalle regole di riduzione della superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="1e77a-229">The table lists all the file names detected by your attack surface reduction rules.</span></span> <span data-ttu-id="1e77a-230">È possibile selezionare i file per esaminare l'impatto dell'esclusione:</span><span class="sxs-lookup"><span data-stu-id="1e77a-230">You can select files to review the impact of excluding them:</span></span>

* <span data-ttu-id="1e77a-231">Quanti meno rilevamenti</span><span class="sxs-lookup"><span data-stu-id="1e77a-231">How many fewer detections</span></span>
* <span data-ttu-id="1e77a-232">Quanti meno dispositivi segnalano i rilevamenti</span><span class="sxs-lookup"><span data-stu-id="1e77a-232">How many fewer devices report the detections</span></span>

<span data-ttu-id="1e77a-233">Per ottenere un elenco dei file selezionati con i percorsi completi per l'esclusione, selezionare **Ottieni percorsi di esclusione**.</span><span class="sxs-lookup"><span data-stu-id="1e77a-233">To get a list of the selected files with their full paths for exclusion, select **Get exclusion paths**.</span></span>

<span data-ttu-id="1e77a-234">Registri per la regola di ASR **Block Credential Stealing from the Windows Local Security Authority Subsystem (Lsass. exe)** acquisire l'app di origine **Lsass. exe**, un file di sistema normale, come file rilevato.</span><span class="sxs-lookup"><span data-stu-id="1e77a-234">Logs for the ASR rule **Block credential stealing from the Windows local security authority subsystem (lsass.exe)** capture the source app **lsass.exe**, a normal system file, as the detected file.</span></span> <span data-ttu-id="1e77a-235">Di conseguenza, l'elenco generato dei percorsi di esclusione includerà questo file.</span><span class="sxs-lookup"><span data-stu-id="1e77a-235">As a result, the generated list of exclusion paths will include this file.</span></span> <span data-ttu-id="1e77a-236">Per escludere il file che ha attivato questa regola anziché **Lsass. exe**, utilizzare il percorso dell'applicazione di origine anziché il file rilevato.</span><span class="sxs-lookup"><span data-stu-id="1e77a-236">To exclude the file that triggered this rule instead of **lsass.exe**, use the path to the source app instead of the detected file.</span></span>

<span data-ttu-id="1e77a-237">Per individuare l'app di origine, eseguire la [query di ricerca avanzata](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) seguente per questa regola specifica (identificata dalla regola ID 9e6c4e1f-7d60-472F-ba1a-a39ef669e4b2):</span><span class="sxs-lookup"><span data-stu-id="1e77a-237">To locate the source app, run the following [advanced hunting query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) for this specific rule (identified by rule ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a><span data-ttu-id="1e77a-238">Controllare i file per l'esclusione</span><span class="sxs-lookup"><span data-stu-id="1e77a-238">Check files for exclusion</span></span>

<span data-ttu-id="1e77a-239">Prima di escludere un file dal riconoscimento vocale automatico, è consigliabile ispezionare il file per determinare se non è effettivamente dannoso.</span><span class="sxs-lookup"><span data-stu-id="1e77a-239">Before excluding a file from ASR, we recommend that you inspect the file to determine if it is indeed not malicious.</span></span>

<span data-ttu-id="1e77a-240">Per esaminare un file, utilizzare la [pagina informazioni sui file](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="1e77a-240">To review a file, use the [file information page](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) on Microsoft Defender Security Center.</span></span> <span data-ttu-id="1e77a-241">La pagina fornisce informazioni sulla prevalenza così come il rapporto di rilevamento antivirus di VirusTotal.</span><span class="sxs-lookup"><span data-stu-id="1e77a-241">The page provides prevalence information as well as the VirusTotal antivirus detection ratio.</span></span> <span data-ttu-id="1e77a-242">È inoltre possibile utilizzare la pagina per inviare il file per un'analisi approfondita.</span><span class="sxs-lookup"><span data-stu-id="1e77a-242">You can also use the page to submit the file for deep analysis.</span></span>

<span data-ttu-id="1e77a-243">Per individuare un file rilevato in Microsoft Defender Security Center, cercare tutti i rilevamenti ASR utilizzando la query di caccia avanzata seguente:</span><span class="sxs-lookup"><span data-stu-id="1e77a-243">To locate a detected file in Microsoft Defender Security Center, search for all ASR detections using the following advanced hunting query:</span></span>

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

<span data-ttu-id="1e77a-244">Utilizzare l'interfaccia **SHA1** o la **InitiatingProcessSHA1** nei risultati per cercare il file utilizzando la barra di ricerca universale in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="1e77a-244">Use the **SHA1** or the **InitiatingProcessSHA1** in the results to search for the file using the universal search bar in Microsoft Defender Security Center.</span></span>
