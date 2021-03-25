---
title: Visualizzare e organizzare la coda degli avvisi di Microsoft Defender ATP
description: Informazioni sul funzionamento delle code degli avvisi di Microsoft Defender ATP e su come ordinare e filtrare gli elenchi di avvisi.
keywords: avvisi, code, coda degli avvisi, ordinare, ordinare, filtrare, gestire gli avvisi, nuovi, in corso, risolti, più recenti, tempo in coda, gravità, periodo di tempo, avvisi esperti di minacce Microsoft
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
ms.date: 03/27/2020
ms.technology: mde
ms.openlocfilehash: e1c85db5afac70ec4f2520eed55dcc4f3773fd03
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067930"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-alerts-queue"></a><span data-ttu-id="d9339-104">Visualizzare e organizzare la coda di Microsoft Defender for Endpoint Alerts</span><span class="sxs-lookup"><span data-stu-id="d9339-104">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d9339-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d9339-105">**Applies to:**</span></span>
- [<span data-ttu-id="d9339-106">Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="d9339-106">Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="d9339-107">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d9339-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d9339-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="d9339-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-alertsq-abovefoldlink) 

<span data-ttu-id="d9339-109">La **coda Avvisi** mostra un elenco di avvisi contrassegnati dai dispositivi della rete.</span><span class="sxs-lookup"><span data-stu-id="d9339-109">The **Alerts queue** shows a list of alerts that were flagged from devices in your network.</span></span> <span data-ttu-id="d9339-110">Per impostazione predefinita, la coda visualizza gli avvisi visualizzati negli ultimi 30 giorni in una visualizzazione raggruppata.</span><span class="sxs-lookup"><span data-stu-id="d9339-110">By default, the queue displays alerts seen in the last 30 days in a grouped view.</span></span> <span data-ttu-id="d9339-111">Gli avvisi più recenti vengono visualizzati all'inizio dell'elenco per visualizzare prima gli avvisi più recenti.</span><span class="sxs-lookup"><span data-stu-id="d9339-111">The most recent alerts are showed at the top of the list helping you see the most recent alerts first.</span></span>

> [!NOTE]
> <span data-ttu-id="d9339-112">La coda degli avvisi è notevolmente ridotta con l'analisi e la correzione automatizzate, consentendo agli esperti delle operazioni di sicurezza di concentrarsi su minacce più sofisticate e altre iniziative di alto valore.</span><span class="sxs-lookup"><span data-stu-id="d9339-112">The alerts queue is significantly reduced with automated investigation and remediation, allowing security operations experts to focus on more sophisticated threats and other high value initiatives.</span></span> <span data-ttu-id="d9339-113">Quando un avviso contiene un'entità supportata per l'indagine automatizzata (ad esempio, un file) in un dispositivo con un sistema operativo supportato, è possibile avviare un'indagine e una correzione automatizzate.</span><span class="sxs-lookup"><span data-stu-id="d9339-113">When an alert contains a supported entity for automated investigation (for example, a file) in a device that has a supported operating system for it, an automated investigation and remediation can start.</span></span> <span data-ttu-id="d9339-114">Per ulteriori informazioni sulle indagini automatizzate, vedere [Overview of Automated investigations](automated-investigations.md).</span><span class="sxs-lookup"><span data-stu-id="d9339-114">For more information on automated investigations, see [Overview of Automated investigations](automated-investigations.md).</span></span>

<span data-ttu-id="d9339-115">Sono disponibili diverse opzioni tra cui è possibile scegliere per personalizzare la visualizzazione della coda degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="d9339-115">There are several options you can choose from to customize the alerts queue view.</span></span> 

<span data-ttu-id="d9339-116">Nella barra di spostamento superiore è possibile:</span><span class="sxs-lookup"><span data-stu-id="d9339-116">On the top navigation you can:</span></span>

- <span data-ttu-id="d9339-117">Selezionare la visualizzazione raggruppata o la visualizzazione elenco</span><span class="sxs-lookup"><span data-stu-id="d9339-117">Select grouped view or list view</span></span>
- <span data-ttu-id="d9339-118">Personalizzare le colonne per aggiungere o rimuovere colonne</span><span class="sxs-lookup"><span data-stu-id="d9339-118">Customize columns to add or remove columns</span></span> 
- <span data-ttu-id="d9339-119">Selezionare gli elementi da visualizzare per pagina</span><span class="sxs-lookup"><span data-stu-id="d9339-119">Select the items to show per page</span></span>
- <span data-ttu-id="d9339-120">Spostarsi tra le pagine</span><span class="sxs-lookup"><span data-stu-id="d9339-120">Navigate between pages</span></span>
- <span data-ttu-id="d9339-121">Applicazione di filtri</span><span class="sxs-lookup"><span data-stu-id="d9339-121">Apply filters</span></span>

![Immagine della coda degli avvisi](images/alerts-queue-list.png)

## <a name="sort-filter-and-group-the-alerts-queue"></a><span data-ttu-id="d9339-123">Ordinare, filtrare e raggruppare la coda degli avvisi</span><span class="sxs-lookup"><span data-stu-id="d9339-123">Sort, filter, and group the alerts queue</span></span>

<span data-ttu-id="d9339-124">È possibile applicare i filtri seguenti per limitare l'elenco degli avvisi e ottenere una visualizzazione più mirata degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="d9339-124">You can apply the following filters to limit the list of alerts and get a more focused view the alerts.</span></span>

### <a name="severity"></a><span data-ttu-id="d9339-125">Gravità</span><span class="sxs-lookup"><span data-stu-id="d9339-125">Severity</span></span>

<span data-ttu-id="d9339-126">Gravità avviso</span><span class="sxs-lookup"><span data-stu-id="d9339-126">Alert severity</span></span> | <span data-ttu-id="d9339-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d9339-127">Description</span></span>
:---|:---
<span data-ttu-id="d9339-128">Alto</span><span class="sxs-lookup"><span data-stu-id="d9339-128">High</span></span> </br><span data-ttu-id="d9339-129">(Rosso)</span><span class="sxs-lookup"><span data-stu-id="d9339-129">(Red)</span></span> | <span data-ttu-id="d9339-130">Avvisi comunemente visualizzati associati a minacce persistenti avanzate (APT).</span><span class="sxs-lookup"><span data-stu-id="d9339-130">Alerts commonly seen associated with advanced persistent threats (APT).</span></span> <span data-ttu-id="d9339-131">Questi avvisi indicano un rischio elevato a causa della gravità dei danni che possono infliggere ai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="d9339-131">These alerts indicate a high risk because of  the severity of damage they can inflict on devices.</span></span> <span data-ttu-id="d9339-132">Alcuni esempi sono: attività degli strumenti di furto di credenziali, attività ransomware non associate ad alcun gruppo, manomissione di sensori di sicurezza o attività dannose indicative di un avversario umano.</span><span class="sxs-lookup"><span data-stu-id="d9339-132">Some examples are: credential theft tools activities, ransomware activities not associated with any group, tampering with security sensors, or any malicious activities indicative of a human adversary.</span></span>
<span data-ttu-id="d9339-133">Medio</span><span class="sxs-lookup"><span data-stu-id="d9339-133">Medium</span></span> </br><span data-ttu-id="d9339-134">(Arancione)</span><span class="sxs-lookup"><span data-stu-id="d9339-134">(Orange)</span></span> | <span data-ttu-id="d9339-135">Avvisi relativi al rilevamento degli endpoint e ai comportamenti di risposta post-violazione che potrebbero far parte di una minaccia persistente avanzata (APT).</span><span class="sxs-lookup"><span data-stu-id="d9339-135">Alerts from endpoint detection and response post-breach behaviors that might be a part of an advanced persistent threat (APT).</span></span> <span data-ttu-id="d9339-136">Ciò include comportamenti osservati tipici delle fasi di attacco, modifiche anomali del Registro di sistema, esecuzione di file sospetti e così via.</span><span class="sxs-lookup"><span data-stu-id="d9339-136">This includes observed behaviors typical of attack stages, anomalous registry change, execution of suspicious files, and so forth.</span></span> <span data-ttu-id="d9339-137">Anche se alcuni potrebbero essere parte dei test di sicurezza interni, richiede un'indagine perché potrebbe anche essere parte di un attacco avanzato.</span><span class="sxs-lookup"><span data-stu-id="d9339-137">Although some might be part of internal security testing, it requires investigation as it might also be a part of an advanced attack.</span></span>
<span data-ttu-id="d9339-138">Basso</span><span class="sxs-lookup"><span data-stu-id="d9339-138">Low</span></span> </br><span data-ttu-id="d9339-139">(Giallo)</span><span class="sxs-lookup"><span data-stu-id="d9339-139">(Yellow)</span></span> | <span data-ttu-id="d9339-140">Avvisi sulle minacce associate al malware prevalente.</span><span class="sxs-lookup"><span data-stu-id="d9339-140">Alerts on threats associated with prevalent malware.</span></span> <span data-ttu-id="d9339-141">Ad esempio, strumenti di hacking, strumenti di hacking non malware, come l'esecuzione di comandi di esplorazione, la cancellazione dei registri e così via, che spesso non indicano una minaccia avanzata per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d9339-141">For example, hack-tools, non-malware hack tools, such as running exploration commands, clearing logs, etc., that often do not indicate an advanced threat targeting the organization.</span></span> <span data-ttu-id="d9339-142">Potrebbe anche derivare da un test isolato degli strumenti di sicurezza da parte di un utente dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d9339-142">It could also come from an isolated security tool testing by a user in your organization.</span></span>
<span data-ttu-id="d9339-143">Informativo</span><span class="sxs-lookup"><span data-stu-id="d9339-143">Informational</span></span> </br><span data-ttu-id="d9339-144">(Grigio)</span><span class="sxs-lookup"><span data-stu-id="d9339-144">(Grey)</span></span> | <span data-ttu-id="d9339-145">Avvisi che potrebbero non essere considerati dannosi per la rete, ma che possono aumentare la consapevolezza della sicurezza dell'organizzazione su potenziali problemi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d9339-145">Alerts that might not be considered harmful to the network but can drive organizational security awareness on potential security issues.</span></span>

#### <a name="understanding-alert-severity"></a><span data-ttu-id="d9339-146">Informazioni sulla gravità degli avvisi</span><span class="sxs-lookup"><span data-stu-id="d9339-146">Understanding alert severity</span></span>

<span data-ttu-id="d9339-147">Le gravità degli avvisi di Microsoft Defender Antivirus (Microsoft Defender AV) e Defender for Endpoint sono diverse perché rappresentano ambiti diversi.</span><span class="sxs-lookup"><span data-stu-id="d9339-147">Microsoft Defender Antivirus (Microsoft Defender AV) and Defender for Endpoint alert severities are different because they represent different scopes.</span></span>

<span data-ttu-id="d9339-148">La gravità della minaccia di Microsoft Defender AV rappresenta la gravità assoluta della minaccia rilevata (malware) e viene assegnata in base al potenziale rischio per il singolo dispositivo, se infetto.</span><span class="sxs-lookup"><span data-stu-id="d9339-148">The Microsoft Defender AV threat severity represents the absolute severity of the detected threat (malware), and is assigned based on the potential risk to the individual device, if infected.</span></span>

<span data-ttu-id="d9339-149">La gravità dell'avviso Defender for Endpoint rappresenta la gravità del comportamento rilevato, il rischio effettivo per il dispositivo, ma soprattutto il potenziale rischio per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d9339-149">The Defender for Endpoint alert severity represents the severity of the detected behavior, the actual risk to the device but more importantly the potential risk to the organization.</span></span>

<span data-ttu-id="d9339-150">Quindi, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d9339-150">So, for example:</span></span>

- <span data-ttu-id="d9339-151">La gravità di un avviso defender per endpoint su una minaccia rilevata da Microsoft Defender AV che è stata completamente impedita e che non ha infettato il dispositivo è classificata come "informativo" perché non si è verificata alcuna minaccia effettiva.</span><span class="sxs-lookup"><span data-stu-id="d9339-151">The severity of a Defender for Endpoint alert about a Microsoft Defender AV detected threat that was completely prevented and did not infect the device is categorized as "Informational" because there was no actual damage.</span></span>
- <span data-ttu-id="d9339-152">Un avviso su un malware commerciale è stato rilevato durante l'esecuzione, ma è stato bloccato e corretti da Microsoft Defender AV, è classificato come "Basso" perché potrebbe aver causato alcuni danni al singolo dispositivo, ma non rappresenta alcuna minaccia dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d9339-152">An alert about a commercial malware was detected while executing, but blocked and remediated by Microsoft Defender AV, is categorized as  "Low" because it may have caused some damage to the individual device but poses no organizational threat.</span></span>
- <span data-ttu-id="d9339-153">Un avviso sul malware rilevato durante l'esecuzione che può rappresentare una minaccia non solo per il singolo dispositivo ma per l'organizzazione, indipendentemente dal fatto che sia stato bloccato alla fine, può essere classificato come "Medio" o "Alto".</span><span class="sxs-lookup"><span data-stu-id="d9339-153">An alert about malware detected while executing which can pose a threat not only to the individual device but to the organization, regardless if it was eventually blocked, may be ranked as "Medium" or "High".</span></span>
- <span data-ttu-id="d9339-154">Gli avvisi comportamentali sospetti, che non sono stati bloccati o corretti, verranno classificati come "Low", "Medium" o "High" seguendo le stesse considerazioni sulle minacce organizzative.</span><span class="sxs-lookup"><span data-stu-id="d9339-154">Suspicious behavioral alerts, which weren't blocked or remediated will be ranked "Low", "Medium" or "High" following the same organizational threat considerations.</span></span>

#### <a name="understanding-alert-categories"></a><span data-ttu-id="d9339-155">Informazioni sulle categorie di avviso</span><span class="sxs-lookup"><span data-stu-id="d9339-155">Understanding alert categories</span></span>

<span data-ttu-id="d9339-156">Abbiamo ridefinito le categorie di avviso per allinearsi alle [tattiche](https://attack.mitre.org/tactics/enterprise/) di attacco aziendale nella matrice [MITRE ATT&CK](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="d9339-156">We've redefined the alert categories to align to the [enterprise attack tactics](https://attack.mitre.org/tactics/enterprise/) in the [MITRE ATT&CK matrix](https://attack.mitre.org/).</span></span> <span data-ttu-id="d9339-157">I nuovi nomi di categoria si applicano a tutti i nuovi avvisi.</span><span class="sxs-lookup"><span data-stu-id="d9339-157">New category names apply to all new alerts.</span></span> <span data-ttu-id="d9339-158">Gli avvisi esistenti manderanno i nomi delle categorie precedenti.</span><span class="sxs-lookup"><span data-stu-id="d9339-158">Existing alerts will keep the previous category names.</span></span>

<span data-ttu-id="d9339-159">Nella tabella seguente sono elencate le categorie correnti e il modo in cui vengono in genere mappate alle categorie precedenti.</span><span class="sxs-lookup"><span data-stu-id="d9339-159">The table below lists the current categories and how they generally map to previous categories.</span></span> 

| <span data-ttu-id="d9339-160">Nuova categoria</span><span class="sxs-lookup"><span data-stu-id="d9339-160">New   category</span></span>       | <span data-ttu-id="d9339-161">Nome categoria API</span><span class="sxs-lookup"><span data-stu-id="d9339-161">API category name</span></span>   | <span data-ttu-id="d9339-162">Attività o componente delle minacce rilevate</span><span class="sxs-lookup"><span data-stu-id="d9339-162">Detected threat activity or   component</span></span>                                                                                                 |
|----------------------|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="d9339-163">Raccolta</span><span class="sxs-lookup"><span data-stu-id="d9339-163">Collection</span></span>           | <span data-ttu-id="d9339-164">Raccolta</span><span class="sxs-lookup"><span data-stu-id="d9339-164">Collection</span></span>          | <span data-ttu-id="d9339-165">Individuazione e raccolta di dati per l'esfiltrazione</span><span class="sxs-lookup"><span data-stu-id="d9339-165">Locating   and collecting data for exfiltration</span></span>                                                                                         |
| <span data-ttu-id="d9339-166">Comando e controllo</span><span class="sxs-lookup"><span data-stu-id="d9339-166">Command and control</span></span>  | <span data-ttu-id="d9339-167">CommandAndControl</span><span class="sxs-lookup"><span data-stu-id="d9339-167">CommandAndControl</span></span>   | <span data-ttu-id="d9339-168">Connessione all'infrastruttura di rete controllata da un utente malintenzionato per inoltrare dati o ricevere comandi</span><span class="sxs-lookup"><span data-stu-id="d9339-168">Connecting   to attacker-controlled network infrastructure to relay data or receive   commands</span></span>                                          |
| <span data-ttu-id="d9339-169">Accesso alle credenziali</span><span class="sxs-lookup"><span data-stu-id="d9339-169">Credential access</span></span>    | <span data-ttu-id="d9339-170">CredentialAccess</span><span class="sxs-lookup"><span data-stu-id="d9339-170">CredentialAccess</span></span>    | <span data-ttu-id="d9339-171">Ottenere credenziali valide per estendere il controllo su dispositivi e altre risorse nella rete</span><span class="sxs-lookup"><span data-stu-id="d9339-171">Obtaining   valid credentials to extend control over devices and other resources in the   network</span></span>                                       |
| <span data-ttu-id="d9339-172">Evasione della difesa</span><span class="sxs-lookup"><span data-stu-id="d9339-172">Defense evasion</span></span>      | <span data-ttu-id="d9339-173">DefenseEvasion</span><span class="sxs-lookup"><span data-stu-id="d9339-173">DefenseEvasion</span></span>      | <span data-ttu-id="d9339-174">Evitare i controlli di sicurezza, ad esempio disattivando le app di sicurezza, eliminando gli impianto e eseguendo rootkit</span><span class="sxs-lookup"><span data-stu-id="d9339-174">Avoiding security controls by, for example, turning off   security apps, deleting implants, and running rootkits</span></span>                        |
| <span data-ttu-id="d9339-175">Individuazione</span><span class="sxs-lookup"><span data-stu-id="d9339-175">Discovery</span></span>            | <span data-ttu-id="d9339-176">Individuazione</span><span class="sxs-lookup"><span data-stu-id="d9339-176">Discovery</span></span>           | <span data-ttu-id="d9339-177">Raccolta di informazioni su dispositivi e risorse importanti, ad esempio computer di amministratore, controller di dominio e file server</span><span class="sxs-lookup"><span data-stu-id="d9339-177">Gathering   information about important devices and resources, such as administrator   computers, domain controllers, and file servers</span></span>  |
| <span data-ttu-id="d9339-178">Esecuzione</span><span class="sxs-lookup"><span data-stu-id="d9339-178">Execution</span></span>            | <span data-ttu-id="d9339-179">Esecuzione</span><span class="sxs-lookup"><span data-stu-id="d9339-179">Execution</span></span>           | <span data-ttu-id="d9339-180">Avvio di strumenti di attacco e codice dannoso, tra cui RATI e backdoor</span><span class="sxs-lookup"><span data-stu-id="d9339-180">Launching   attacker tools and malicious code, including RATs and backdoors</span></span>                                                             |
| <span data-ttu-id="d9339-181">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="d9339-181">Exfiltration</span></span>         | <span data-ttu-id="d9339-182">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="d9339-182">Exfiltration</span></span>        | <span data-ttu-id="d9339-183">Estrazione dei dati dalla rete in una posizione esterna controllata da un utente malintenzionato</span><span class="sxs-lookup"><span data-stu-id="d9339-183">Extracting   data from the network to an external, attacker-controlled location</span></span>                                                         |
| <span data-ttu-id="d9339-184">Exploit</span><span class="sxs-lookup"><span data-stu-id="d9339-184">Exploit</span></span>              | <span data-ttu-id="d9339-185">Exploit</span><span class="sxs-lookup"><span data-stu-id="d9339-185">Exploit</span></span>             | <span data-ttu-id="d9339-186">Codice di exploit e possibile attività di sfruttamento</span><span class="sxs-lookup"><span data-stu-id="d9339-186">Exploit   code and possible exploitation activity</span></span>                                                                                       |
| <span data-ttu-id="d9339-187">Accesso iniziale</span><span class="sxs-lookup"><span data-stu-id="d9339-187">Initial access</span></span>       | <span data-ttu-id="d9339-188">InitialAccess</span><span class="sxs-lookup"><span data-stu-id="d9339-188">InitialAccess</span></span>       | <span data-ttu-id="d9339-189">Ottenere l'immissione iniziale nella rete di destinazione, in genere con tentativi di indovinare password, exploit o messaggi di posta elettronica di phishing</span><span class="sxs-lookup"><span data-stu-id="d9339-189">Gaining   initial entry to the target network, usually involving password-guessing,   exploits, or phishing emails</span></span>                      |
| <span data-ttu-id="d9339-190">Movimento laterale</span><span class="sxs-lookup"><span data-stu-id="d9339-190">Lateral movement</span></span>     | <span data-ttu-id="d9339-191">LateralMovement</span><span class="sxs-lookup"><span data-stu-id="d9339-191">LateralMovement</span></span>     | <span data-ttu-id="d9339-192">Spostamento tra dispositivi nella rete di destinazione per raggiungere risorse critiche o ottenere la persistenza della rete</span><span class="sxs-lookup"><span data-stu-id="d9339-192">Moving   between devices in the target network to reach critical resources or gain   network persistence</span></span>                                |
| <span data-ttu-id="d9339-193">Malware</span><span class="sxs-lookup"><span data-stu-id="d9339-193">Malware</span></span>              | <span data-ttu-id="d9339-194">Malware</span><span class="sxs-lookup"><span data-stu-id="d9339-194">Malware</span></span>             | <span data-ttu-id="d9339-195">Backdoor, trojan e altri tipi di codice dannoso</span><span class="sxs-lookup"><span data-stu-id="d9339-195">Backdoors,   trojans, and other types of malicious code</span></span>                                                                                 |
| <span data-ttu-id="d9339-196">Persistenza</span><span class="sxs-lookup"><span data-stu-id="d9339-196">Persistence</span></span>          | <span data-ttu-id="d9339-197">Persistenza</span><span class="sxs-lookup"><span data-stu-id="d9339-197">Persistence</span></span>         | <span data-ttu-id="d9339-198">Creazione di punti di estendibilità dell'avvio automatico (ASEP) per rimanere attivi e superare i riavvii del sistema</span><span class="sxs-lookup"><span data-stu-id="d9339-198">Creating   autostart extensibility points (ASEPs) to remain active and survive system   restarts</span></span>                                        |
| <span data-ttu-id="d9339-199">Escalation dei privilegi</span><span class="sxs-lookup"><span data-stu-id="d9339-199">Privilege escalation</span></span> | <span data-ttu-id="d9339-200">PrivilegeEscalation</span><span class="sxs-lookup"><span data-stu-id="d9339-200">PrivilegeEscalation</span></span> | <span data-ttu-id="d9339-201">Ottenere livelli di autorizzazione superiori per il codice eseguendolo nel contesto di un processo o di un account con privilegi</span><span class="sxs-lookup"><span data-stu-id="d9339-201">Obtaining   higher permission levels for code by running it in the context of a   privileged process or account</span></span>                         |
| <span data-ttu-id="d9339-202">Ransomware</span><span class="sxs-lookup"><span data-stu-id="d9339-202">Ransomware</span></span>           | <span data-ttu-id="d9339-203">Ransomware</span><span class="sxs-lookup"><span data-stu-id="d9339-203">Ransomware</span></span>          | <span data-ttu-id="d9339-204">Malware che crittografa i file ed estorce il pagamento per ripristinare l'accesso</span><span class="sxs-lookup"><span data-stu-id="d9339-204">Malware   that encrypts files and extorts payment to restore access</span></span>                                                                     |
| <span data-ttu-id="d9339-205">Attività sospette</span><span class="sxs-lookup"><span data-stu-id="d9339-205">Suspicious activity</span></span>  | <span data-ttu-id="d9339-206">SuspiciousActivity</span><span class="sxs-lookup"><span data-stu-id="d9339-206">SuspiciousActivity</span></span>  | <span data-ttu-id="d9339-207">Attività atipiche che potrebbero essere attività di malware o parte di un attacco</span><span class="sxs-lookup"><span data-stu-id="d9339-207">Atypical   activity that could be malware activity or part of an attack</span></span>                                                                 |
| <span data-ttu-id="d9339-208">Software indesiderato</span><span class="sxs-lookup"><span data-stu-id="d9339-208">Unwanted software</span></span>    | <span data-ttu-id="d9339-209">UnwantedSoftware</span><span class="sxs-lookup"><span data-stu-id="d9339-209">UnwantedSoftware</span></span>    | <span data-ttu-id="d9339-210">App e app di bassa reputazione che influiscono sulla produttività e sull'esperienza utente; rilevato come applicazioni potenzialmente indesiderate (PUA)</span><span class="sxs-lookup"><span data-stu-id="d9339-210">Low-reputation   apps and apps that impact productivity and the user experience; detected as   potentially unwanted applications (PUAs)</span></span> |

### <a name="status"></a><span data-ttu-id="d9339-211">Stato</span><span class="sxs-lookup"><span data-stu-id="d9339-211">Status</span></span>

<span data-ttu-id="d9339-212">È possibile scegliere di limitare l'elenco di avvisi in base al relativo stato.</span><span class="sxs-lookup"><span data-stu-id="d9339-212">You can choose to limit the list of alerts based on their status.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="d9339-213">Stato dell'indagine</span><span class="sxs-lookup"><span data-stu-id="d9339-213">Investigation state</span></span>

<span data-ttu-id="d9339-214">Corrisponde allo stato di analisi automatica.</span><span class="sxs-lookup"><span data-stu-id="d9339-214">Corresponds to the automated investigation state.</span></span>

### <a name="category"></a><span data-ttu-id="d9339-215">Category</span><span class="sxs-lookup"><span data-stu-id="d9339-215">Category</span></span>

<span data-ttu-id="d9339-216">È possibile scegliere di filtrare la coda per visualizzare tipi specifici di attività dannose.</span><span class="sxs-lookup"><span data-stu-id="d9339-216">You can choose to filter the queue to display specific types of malicious activity.</span></span>

### <a name="assigned-to"></a><span data-ttu-id="d9339-217">Assegnata a</span><span class="sxs-lookup"><span data-stu-id="d9339-217">Assigned to</span></span>

<span data-ttu-id="d9339-218">Puoi scegliere tra la visualizzazione degli avvisi assegnati all'utente o l'automazione.</span><span class="sxs-lookup"><span data-stu-id="d9339-218">You can choose between showing alerts that are assigned to you or automation.</span></span>

### <a name="detection-source"></a><span data-ttu-id="d9339-219">Origine di rilevamento</span><span class="sxs-lookup"><span data-stu-id="d9339-219">Detection source</span></span>

<span data-ttu-id="d9339-220">Selezionare l'origine che ha attivato il rilevamento degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="d9339-220">Select the source that triggered the alert detection.</span></span> <span data-ttu-id="d9339-221">I partecipanti all'anteprima di Microsoft Threat Experts possono ora filtrare e visualizzare i rilevamenti del nuovo servizio di ricerca gestito da esperti di minacce.</span><span class="sxs-lookup"><span data-stu-id="d9339-221">Microsoft Threat Experts preview participants can now filter and see detections from the new threat experts-managed hunting service.</span></span>

>[!NOTE]
><span data-ttu-id="d9339-222">Il filtro Antivirus verrà visualizzato solo se i dispositivi usano Microsoft Defender Antivirus come prodotto antimalware di protezione in tempo reale predefinito.</span><span class="sxs-lookup"><span data-stu-id="d9339-222">The Antivirus filter will only appear if devices are using Microsoft Defender Antivirus as the default real-time protection antimalware product.</span></span>

| <span data-ttu-id="d9339-223">Origine di rilevamento</span><span class="sxs-lookup"><span data-stu-id="d9339-223">Detection source</span></span>                  | <span data-ttu-id="d9339-224">Valore API</span><span class="sxs-lookup"><span data-stu-id="d9339-224">API value</span></span>                  |
|-----------------------------------|----------------------------|
| <span data-ttu-id="d9339-225">Sensori di terze parti</span><span class="sxs-lookup"><span data-stu-id="d9339-225">3rd party sensors</span></span>                 | <span data-ttu-id="d9339-226">ThirdPartySensors</span><span class="sxs-lookup"><span data-stu-id="d9339-226">ThirdPartySensors</span></span>          |
| <span data-ttu-id="d9339-227">Antivirus</span><span class="sxs-lookup"><span data-stu-id="d9339-227">Antivirus</span></span>                         | <span data-ttu-id="d9339-228">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="d9339-228">WindowsDefenderAv</span></span>          |
| <span data-ttu-id="d9339-229">Indagine automatizzata</span><span class="sxs-lookup"><span data-stu-id="d9339-229">Automated investigation</span></span>           | <span data-ttu-id="d9339-230">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="d9339-230">AutomatedInvestigation</span></span>     |
| <span data-ttu-id="d9339-231">Rilevamento personalizzato</span><span class="sxs-lookup"><span data-stu-id="d9339-231">Custom detection</span></span>                  | <span data-ttu-id="d9339-232">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="d9339-232">CustomDetection</span></span>            |
| <span data-ttu-id="d9339-233">Ti personalizzato</span><span class="sxs-lookup"><span data-stu-id="d9339-233">Custom TI</span></span>                         | <span data-ttu-id="d9339-234">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="d9339-234">CustomerTI</span></span>                 |
| <span data-ttu-id="d9339-235">EDR</span><span class="sxs-lookup"><span data-stu-id="d9339-235">EDR</span></span>                               | <span data-ttu-id="d9339-236">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="d9339-236">WindowsDefenderAtp</span></span>         |
| <span data-ttu-id="d9339-237">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9339-237">Microsoft 365 Defender</span></span>            | <span data-ttu-id="d9339-238">MTP</span><span class="sxs-lookup"><span data-stu-id="d9339-238">MTP</span></span>                        |
| <span data-ttu-id="d9339-239">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="d9339-239">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="d9339-240">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="d9339-240">OfficeATP</span></span>                  |
| <span data-ttu-id="d9339-241">Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="d9339-241">Microsoft Threat Experts</span></span>          | <span data-ttu-id="d9339-242">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="d9339-242">ThreatExperts</span></span>              |
| <span data-ttu-id="d9339-243">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="d9339-243">SmartScreen</span></span>                       | <span data-ttu-id="d9339-244">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="d9339-244">WindowsDefenderSmartScreen</span></span> |

### <a name="os-platform"></a><span data-ttu-id="d9339-245">Piattaforma del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="d9339-245">OS platform</span></span>

<span data-ttu-id="d9339-246">Limita la visualizzazione della coda degli avvisi selezionando la piattaforma del sistema operativo che vuoi analizzare.</span><span class="sxs-lookup"><span data-stu-id="d9339-246">Limit the alerts queue view by selecting the OS platform that you're interested in investigating.</span></span>

### <a name="device-group"></a><span data-ttu-id="d9339-247">Gruppo di dispositivi</span><span class="sxs-lookup"><span data-stu-id="d9339-247">Device group</span></span>

<span data-ttu-id="d9339-248">Se hai gruppi di dispositivi specifici che vuoi controllare, puoi selezionare i gruppi per limitare la visualizzazione della coda degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="d9339-248">If you have specific device groups that you're interested in checking, you can select the groups to limit the alerts queue view.</span></span> 

### <a name="associated-threat"></a><span data-ttu-id="d9339-249">Minaccia associata</span><span class="sxs-lookup"><span data-stu-id="d9339-249">Associated threat</span></span>

<span data-ttu-id="d9339-250">Utilizzare questo filtro per concentrarsi sugli avvisi correlati alle minacce di alto profilo.</span><span class="sxs-lookup"><span data-stu-id="d9339-250">Use this filter to focus on alerts that are related to high profile threats.</span></span> <span data-ttu-id="d9339-251">È possibile visualizzare l'elenco completo delle minacce di alto profilo in [Analisi delle minacce](threat-analytics.md).</span><span class="sxs-lookup"><span data-stu-id="d9339-251">You can see the full list of high-profile threats in [Threat analytics](threat-analytics.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d9339-252">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d9339-252">Related topics</span></span>

- [<span data-ttu-id="d9339-253">Gestire gli avvisi di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d9339-253">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="d9339-254">Analizzare gli avvisi di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d9339-254">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="d9339-255">Analizzare un file associato a un avviso di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d9339-255">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="d9339-256">Analizzare i dispositivi nell'elenco Di Microsoft Defender per dispositivi endpoint</span><span class="sxs-lookup"><span data-stu-id="d9339-256">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="d9339-257">Analizzare un indirizzo IP associato a un avviso di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d9339-257">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="d9339-258">Analizzare un dominio associato a un avviso di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d9339-258">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="d9339-259">Analizzare un account utente in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d9339-259">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)