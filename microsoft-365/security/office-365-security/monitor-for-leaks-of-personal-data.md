---
title: Monitorare la perdita di dati personali
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MET150
description: Informazioni su tre strumenti che è possibile utilizzare per monitorare la perdita di dati personali.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b51bc5d5d3cbfa8951392f88edc6e178778206df
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921253"
---
# <a name="monitor-for-leaks-of-personal-data"></a><span data-ttu-id="7efef-103">Monitorare la perdita di dati personali</span><span class="sxs-lookup"><span data-stu-id="7efef-103">Monitor for leaks of personal data</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="7efef-p101">Sono disponibili molti strumenti che è possibile utilizzare per monitorare l'uso e il trasporto dei dati personali. In questo argomento ne vengono descritti tre.</span><span class="sxs-lookup"><span data-stu-id="7efef-p101">There are many tools that can be used to monitor the use and transport of personal data. This topic describes three tools that work well.</span></span>

![Strumenti per monitorare l'uso e il trasporto dei dati personali](../../media/Monitor-for-leaks-of-personal-data-image1.png)

<span data-ttu-id="7efef-107">Nella figura:</span><span class="sxs-lookup"><span data-stu-id="7efef-107">In the illustration:</span></span>

- <span data-ttu-id="7efef-p102">Iniziare con i report sulla prevenzione della perdita dei dati di Microsoft 365 per il monitoraggio dei dati personali in SharePoint Online, OneDrive for Business e della posta elettronica in transito. Tali report forniscono il massimo livello di informazioni dettagliate per il monitoraggio dei dati personali. Tuttavia, non includono tutti i servizi in Office 365.</span><span class="sxs-lookup"><span data-stu-id="7efef-p102">Start with Microsoft 365 data loss prevention reports for monitoring personal data in SharePoint Online, OneDrive for Business, and email in transit. These reports provide the greatest level of detail for monitoring personal data. However, these reports don't include all services in Office 365.</span></span>

- <span data-ttu-id="7efef-p103">Successivamente, usare i criteri di avviso e i log di controllo per monitorare l'attività nei servizi. Configurare il monitoraggio continuo o cercare nel log di controllo per analizzare un incidente. Il log di controllo è supportato da vari servizi: Sway, PowerBI, eDiscovery, Dynamics 365, Microsoft Flow, Microsoft Teams, Attività amministrative, OneDrive for Business, SharePoint Online, posta in transito e cassette postali inattive. Le conversazioni di Skype sono incluse nelle cassette postali inattive.</span><span class="sxs-lookup"><span data-stu-id="7efef-p103">Next, use alert policies and the audit log to monitor activity across services. Set up ongoing monitoring or search the audit log to investigate an incident. The audit log works across services—Sway, Power BI, eDiscovery, Dynamics 365, Microsoft Flow, Microsoft Teams, Admin activity, OneDrive for Business, SharePoint Online, mail in transit, and mailboxes at rest. Skype conversations are included in mailboxes at rest.</span></span>

- <span data-ttu-id="7efef-p104">Infine, usare Microsoft Cloud App Security per monitorare i file con dati sensibili in altri provider SaaS. Presto sarà possibile usare i tipi di informazioni sensibili e le etichette unificate in Azure Information Protection e Office con Cloud App Security. È possibile configurare criteri applicabili a tutte le app SaaS o ad app specifiche (ad esempio, Box). Cloud App Security non rileva i file in Exchange Online, compresi quelli allegati ai messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="7efef-p104">Finally, Use Microsoft Cloud App Security to monitor files with sensitive data in other SaaS providers. Coming soon is the ability to use sensitive information types and unified labels across Azure Information Protection and Office with Cloud App Security. You can set up policies that apply to all of your SaaS apps or specific apps (like Box). Cloud App Security doesn't discover files in Exchange Online, including files attached to email.</span></span>

## <a name="data-loss-prevention-reports"></a><span data-ttu-id="7efef-119">Report sulla prevenzione della perdita di dati</span><span class="sxs-lookup"><span data-stu-id="7efef-119">Data loss prevention reports</span></span>

<span data-ttu-id="7efef-p105">Dopo aver creato i criteri di prevenzione della perdita dei dati (DLP), è consigliabile verificare che funzionino come previsto e aiutino a mantenere la conformità. Con i report di prevenzione della perdita dei dati in Office 365, è possibile visualizzare rapidamente il numero di corrispondenze, sostituzioni e falsi positivi dei criteri DLP, vederne l'andamento nel corso del tempo, filtrare il report in vari modi ed entrare nei dettagli selezionando un punto nel grafico.</span><span class="sxs-lookup"><span data-stu-id="7efef-p105">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant. With the DLP reports in Office 365, you can quickly view the number of DLP policy matches, overrides, or false positives; see whether they're trending up or down over time; filter the report in different ways; and view more details by selecting a point on a line on the graph.</span></span>

<span data-ttu-id="7efef-122">È possibile utilizzare i report DLP per:</span><span class="sxs-lookup"><span data-stu-id="7efef-122">You can use the DLP reports to:</span></span>

- <span data-ttu-id="7efef-123">Concentrare l'attenzione su intervalli di tempo specifici e comprendere i motivi di eventuali impennate e tendenze.</span><span class="sxs-lookup"><span data-stu-id="7efef-123">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>

- <span data-ttu-id="7efef-124">Individuare i processi aziendali che violano i criteri DLP dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7efef-124">Discover business processes that violate your organization's DLP policies.</span></span>

- <span data-ttu-id="7efef-125">Comprendere l'eventuale impatto aziendale dei criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="7efef-125">Understand any business impact of the DLP policies.</span></span>

- <span data-ttu-id="7efef-126">Visualizzare le giustificazioni inviate dagli utenti quando risolvono un suggerimento per i criteri ignorando il criterio o segnalando un falso positivo.</span><span class="sxs-lookup"><span data-stu-id="7efef-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy or reporting a false positive.</span></span>

- <span data-ttu-id="7efef-127">Verificare la conformità con uno specifico criterio DLP mostrando le eventuali corrispondenze per tale criterio.</span><span class="sxs-lookup"><span data-stu-id="7efef-127">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>

- <span data-ttu-id="7efef-128">Visualizzare un elenco di file con dati riservati corrispondenti ai criteri DLP nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="7efef-128">View a list of files with sensitive data that matches your DLP policies in the details pane.</span></span>

<span data-ttu-id="7efef-129">Inoltre, è possibile utilizzare i report DLP per ottimizzare i criteri DLP, quando vengono eseguiti nella modalità test.</span><span class="sxs-lookup"><span data-stu-id="7efef-129">In addition, you can use the DLP reports to fine-tune your DLP policies as you run them in test mode.</span></span>

<span data-ttu-id="7efef-130">I report DPL sono disponibili nel centro sicurezza e nel centro conformità.</span><span class="sxs-lookup"><span data-stu-id="7efef-130">DLP reports are in the security center and the compliance center.</span></span> <span data-ttu-id="7efef-131">Passare a Report \> Visualizza report.</span><span class="sxs-lookup"><span data-stu-id="7efef-131">Navigate to Reports \> View reports.</span></span> <span data-ttu-id="7efef-132">Sotto Prevenzione della perdita dei dati scegliere Corrispondenze della regola e dei criteri di prevenzione della perdita dei dati o Falsi positivi e override dei criteri di prevenzione della perdita dei dati.</span><span class="sxs-lookup"><span data-stu-id="7efef-132">Under Data loss prevention (DLP), go to either DLP policy and rule matches or DLP false positives and overrides.</span></span>

<span data-ttu-id="7efef-133">Per ulteriori informazioni, vedere [Visualizzare i report di prevenzione della perdita di dati](../../compliance/view-the-dlp-reports.md).</span><span class="sxs-lookup"><span data-stu-id="7efef-133">For more information, see [View the reports for data loss prevention](../../compliance/view-the-dlp-reports.md).</span></span>

![Report che mostra le corrispondenze ai criteri DLP](../../media/Monitor-for-leaks-of-personal-data-image2.png)

## <a name="audit-log-and-alert-policies"></a><span data-ttu-id="7efef-135">Log di controllo e criteri di avviso</span><span class="sxs-lookup"><span data-stu-id="7efef-135">audit log and alert policies</span></span>

<span data-ttu-id="7efef-136">Il log di controllo contiene eventi di Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory, Microsoft Teams, Power BI, Sway e altri servizi.</span><span class="sxs-lookup"><span data-stu-id="7efef-136">The audit log contains events from Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory, Microsoft Teams, Power BI, Sway, and other services.</span></span>

<span data-ttu-id="7efef-137">Il Centro sicurezza e conformità offre due metodi per il monitoraggio e la creazione di report in merito al log di controllo:</span><span class="sxs-lookup"><span data-stu-id="7efef-137">The security center and compliance center provide two ways to monitor and report against the audit log:</span></span>

- <span data-ttu-id="7efef-138">Configurare criteri di avviso, visualizzare avvisi e monitorare le tendenze: utilizzare gli strumenti della dashboard e dei criteri di avviso nel centro sicurezza o nel centro conformità.</span><span class="sxs-lookup"><span data-stu-id="7efef-138">Set up alert policies, view alerts, and monitor trends—Use the alert policy and alert dashboard tools in either the security center or compliance center.</span></span>

- <span data-ttu-id="7efef-p107">Cercare direttamente il log di controllo: è possibile ricercare tutti gli eventi in un intervallo di date specificato o filtrare i risultati in base a criteri specifici, come l'utente che ha effettuato l'operazione, l'operazione o l'oggetto di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7efef-p107">Search the audit log directly: Search for all events in a specified date rage. Or you can filter the results based on specific criteria, such as the user who performed the action, the action, or the target object.</span></span>

<span data-ttu-id="7efef-p108">I team di conformità e sicurezza delle informazioni possono usare questi strumenti per analizzare in modo proattivo le attività eseguite dagli utenti finali e dagli amministratori nei servizi. È possibile configurare avvisi automatici per l'invio di notifiche tramite posta elettronica quando si verificano certe attività su specifiche raccolte siti, ad esempio, quando vengono condivisi contenuti da siti contenenti informazioni correlate al GDPR. Ciò consente a questi team di intervenire presso gli utenti per assicurarsi che rispettino i criteri di sicurezza aziendali o per offrire formazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="7efef-p108">Information security and compliance teams can use these tools to proactively review activities performed by both end users and administrators across services. Automatic alerts can be configured to send email notifications when certain activities occur on specific site collections - for example when content is shared from sites known to contain GDPR-related information. This allows those teams to follow up with users to ensure that corporate security policies are followed, or to provide additional training.</span></span>

<span data-ttu-id="7efef-p109">I team di sicurezza delle informazioni possono anche cercare nel log di controllo per analizzare sospette violazioni dei dati e determinarne l'eventuale causa e gravità. Questa funzionalità integrata agevola la conformità agli articoli 33 e 34 dell'RGPD, secondo i quali le notifiche devono essere fornite all'autorità di supervisione dell'RGPD e ai soggetti dei dati interessati da una violazione dei dati entro uno specifico periodo di tempo. Le voci del log di controllo vengono conservate solo per 90 giorni nel servizio (spesso è consigliabile e molte organizzazioni hanno richiesto un periodo di conservazione di tali log anche maggiore).</span><span class="sxs-lookup"><span data-stu-id="7efef-p109">Information security teams can also search the audit log to investigate suspected data breaches and determine both root cause and the extent of the breach. This built-in capability facilitates compliance with article 33 and 34 of the GDPR, which require notifications be provided to the GDPR supervisory authority and to the data subjects themselves of a data breach within a specific time period. Audit log entries are only retained for 90 days within the service - it is often recommended and many organizations required that these logs be retained for longer periods of time.</span></span>

<span data-ttu-id="7efef-p110">Sono disponibili soluzioni che consentono di sottoscrivere i log di controllo unificati tramite l'API Microsoft Management Activity, di archiviare voci di log secondo necessità e che forniscono dashboard e avvisi avanzati. Un esempio è [Microsoft Operations Management Suite (OMS)](/azure/operations-management-suite/oms-solution-office-365).</span><span class="sxs-lookup"><span data-stu-id="7efef-p110">Solutions are available that subscribe to the Unified Audit Logs through the Microsoft Management Activity API and can both store log entries as needed, and provide advanced dashboards and alerts. One example is [Microsoft Operations Management Suite (OMS)](/azure/operations-management-suite/oms-solution-office-365).</span></span>

<span data-ttu-id="7efef-149">Ulteriori informazioni sui criteri di avviso e sulla ricerca nel log di controllo:</span><span class="sxs-lookup"><span data-stu-id="7efef-149">More information about alert policies and searching the audit log:</span></span>

- [<span data-ttu-id="7efef-150">Criteri di avviso nei centri di sicurezza e di conformità di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7efef-150">Alert policies in the Microsoft 365 security and compliance centers</span></span>](../../compliance/alert-policies.md)

- <span data-ttu-id="7efef-151">[Eseguire ricerche nel il log di controllo per le attività di utente e amministratore in Office 365](../../compliance/search-the-audit-log-in-security-and-compliance.md) (introduzione)</span><span class="sxs-lookup"><span data-stu-id="7efef-151">[Search the audit log for user and admin activity in Office 365](../../compliance/search-the-audit-log-in-security-and-compliance.md) (introduction)</span></span>

- [<span data-ttu-id="7efef-152">Abilitare o disabilitare la ricerca nel log di controllo</span><span class="sxs-lookup"><span data-stu-id="7efef-152">Turn audit log search on or off</span></span>](../../compliance/turn-audit-log-search-on-or-off.md)

- [<span data-ttu-id="7efef-153">Eseguire ricerche nel log di controllo</span><span class="sxs-lookup"><span data-stu-id="7efef-153">Search the audit log</span></span>](../../compliance/search-the-audit-log-in-security-and-compliance.md)

- <span data-ttu-id="7efef-154">[Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) (cmdlet)</span><span class="sxs-lookup"><span data-stu-id="7efef-154">[Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) (cmdlet)</span></span>

- [<span data-ttu-id="7efef-155">Proprietà dettagliate nel log di controllo</span><span class="sxs-lookup"><span data-stu-id="7efef-155">Detailed properties in the audit log</span></span>](../../compliance/detailed-properties-in-the-office-365-audit-log.md)

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="7efef-156">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7efef-156">Microsoft Cloud App Security</span></span>

<span data-ttu-id="7efef-157">Microsoft Cloud App Security consente di individuare altre app SaaS in uso nelle reti e i dati riservati inviati a e da tali app.</span><span class="sxs-lookup"><span data-stu-id="7efef-157">Microsoft Cloud App Security helps you discover other SaaS apps in use across your networks and sensitive data sent to and from these apps.</span></span>

<span data-ttu-id="7efef-p111">Microsoft Cloud App Security è un servizio completo che fornisce visibilità approfondita, controlli più specifici e protezione avanzata dalle minacce per le app cloud. Consente di identificare più di 15.000 applicazioni cloud nei dispositivi collegati alla rete e fornisce l'analisi e la valutazione dei rischi. Non sono richiesti agenti: le informazioni vengono raccolte dai firewall e dai proxy per garantire visibilità completa e contesto per l'uso del cloud e shadow IT.</span><span class="sxs-lookup"><span data-stu-id="7efef-p111">Microsoft Cloud App Security is a comprehensive service providing deep visibility, granular controls, and enhanced threat protection for your cloud apps. It identifies more than 15,000 cloud applications in your network-from all devices-and provides risk scoring and ongoing risk assessment and analytics. No agents required: information is collected from your firewalls and proxies to give you complete visibility and context for cloud usage and shadow IT.</span></span>

<span data-ttu-id="7efef-p112">Per conoscere meglio l'ambiente cloud in uso, la funzionalità di analisi di Cloud App Security fornisce visibilità approfondita nelle attività, nei file e negli account delle app gestite e approvate. È possibile ottenere informazioni dettagliate su un livello di file e individuare dove transitano i dati nelle app cloud.</span><span class="sxs-lookup"><span data-stu-id="7efef-p112">To better understand your cloud environment, the Cloud App Security investigate feature provides deep visibility into all activities, files, and accounts for sanctioned and managed apps. You can gain detailed information on a file level and discover where data travels in the cloud apps.</span></span>

<span data-ttu-id="7efef-163">Ad esempio, nella seguente figura sono illustrati due criteri di Cloud App Security che possono risultare utili con RGPD.</span><span class="sxs-lookup"><span data-stu-id="7efef-163">For examples, the following illustration demonstrates two Cloud App Security policies that can help with GDPR.</span></span>

![Criteri di Cloud App Security di esempio](../../media/Monitor-for-leaks-of-personal-data-image3.png)

<span data-ttu-id="7efef-165">Il primo criterio avvisa quando i file con un attributo PII predefinito o un'espressione personalizzata selezionati vengono condivisi all'esterno dell'organizzazione dalle app SaaS scelte.</span><span class="sxs-lookup"><span data-stu-id="7efef-165">The first policy alerts when files with a predefined PII attribute or custom expression that you choose is shared outside the organization from the SaaS apps that you choose.</span></span>

<span data-ttu-id="7efef-p113">Il secondo criterio blocca i download di file a qualsiasi dispositivo non gestito. Scegliere gli attributi all'interno dei file in cui eseguire la ricerca e delle app SaaS a cui si desidera applicare il criterio.</span><span class="sxs-lookup"><span data-stu-id="7efef-p113">The second policy blocks downloads of files to any unmanaged device. You choose the attributes within the files to look for and the SaaS apps you want the policy to apply to.</span></span>

<span data-ttu-id="7efef-168">Questi tipi di attributi saranno presto disponibili in Cloud App Security:</span><span class="sxs-lookup"><span data-stu-id="7efef-168">These attribute types are coming soon to Cloud App Security:</span></span>

- <span data-ttu-id="7efef-169">Tipi di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="7efef-169">Sensitive information types</span></span>
- <span data-ttu-id="7efef-170">Etichette unificate in Microsoft 365 e Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="7efef-170">Unified labels across Microsoft 365 and Azure Information Protection</span></span>

### <a name="cloud-app-security-dashboard"></a><span data-ttu-id="7efef-171">Dashboard di Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7efef-171">Cloud App Security dashboard</span></span>

<span data-ttu-id="7efef-p114">Se ancora non si usa Cloud App Security, iniziare a configurarlo. Per accedere a Cloud App Security: <https://portal.cloudappsecurity.com>.</span><span class="sxs-lookup"><span data-stu-id="7efef-p114">If you haven't yet started to use Cloud App Security, begin by starting it up. To access Cloud App Security: <https://portal.cloudappsecurity.com>.</span></span>

<span data-ttu-id="7efef-p115">Nota: verificare che "Analizza automaticamente i file per le etichette di classificazione di Azure Information Protection" (nelle impostazioni generali) sia abilitato prima di iniziare a usare Cloud App Security o ad assegnare etichette. Dopo la configurazione, Cloud App Security non ripete l'analisi dei file esistenti finché non vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="7efef-p115">Note: Be sure to enable 'Automatically scan files for Azure Information Protection classification labels' (in General settings) when getting started with Cloud App Security or before you assign labels. After setup, Cloud App Security does not scan existing files again until they are modified.</span></span>

![Dashboard con informazioni sugli avvisi](../../media/Monitor-for-leaks-of-personal-data-image4.png)

<span data-ttu-id="7efef-177">Ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="7efef-177">More information:</span></span>

- [<span data-ttu-id="7efef-178">Distribuzione di Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7efef-178">Deploy Cloud App Security</span></span>](/cloud-app-security/getting-started-with-cloud-app-security)

- [<span data-ttu-id="7efef-179">Ulteriori informazioni su Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7efef-179">More information about Microsoft Cloud App Security</span></span>](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [<span data-ttu-id="7efef-180">Blocco dei download di informazioni sensibili tramite il proxy di Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7efef-180">Block downloads of sensitive information using the Microsoft Cloud App Security proxy</span></span>](/cloud-app-security/use-case-proxy-block-session-aad)

## <a name="example-file-and-activity-policies-to-detect-sharing-of-personal-data"></a><span data-ttu-id="7efef-181">File di esempio e criteri di attività per rilevare la condivisione di dati personali</span><span class="sxs-lookup"><span data-stu-id="7efef-181">Example file and activity policies to detect sharing of personal data</span></span>

### <a name="detect-sharing-of-files-containing-pii--credit-card-number"></a><span data-ttu-id="7efef-182">Individuare la condivisione di file contenenti informazioni personali - Numero di carta di credito</span><span class="sxs-lookup"><span data-stu-id="7efef-182">Detect sharing of files containing PII — Credit card number</span></span>

<span data-ttu-id="7efef-183">L'avviso relativo a un file contenente un numero di carta di credito viene condiviso da un'app cloud approvata.</span><span class="sxs-lookup"><span data-stu-id="7efef-183">Alert when a file containing a credit card number is shared from an approved cloud app.</span></span>

****

|<span data-ttu-id="7efef-184">Controllo</span><span class="sxs-lookup"><span data-stu-id="7efef-184">Control</span></span>|<span data-ttu-id="7efef-185">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="7efef-185">Settings</span></span>|
|---|---|
|<span data-ttu-id="7efef-186">Tipo di criterio</span><span class="sxs-lookup"><span data-stu-id="7efef-186">Policy type</span></span>|<span data-ttu-id="7efef-187">Criteri file</span><span class="sxs-lookup"><span data-stu-id="7efef-187">File policy</span></span>|
|<span data-ttu-id="7efef-188">Modello di criteri</span><span class="sxs-lookup"><span data-stu-id="7efef-188">Policy template</span></span>|<span data-ttu-id="7efef-189">Nessun modello</span><span class="sxs-lookup"><span data-stu-id="7efef-189">No template</span></span>|
|<span data-ttu-id="7efef-190">Gravità del criterio</span><span class="sxs-lookup"><span data-stu-id="7efef-190">Policy severity</span></span>|<span data-ttu-id="7efef-191">Alta</span><span class="sxs-lookup"><span data-stu-id="7efef-191">High</span></span>|
|<span data-ttu-id="7efef-192">Categoria</span><span class="sxs-lookup"><span data-stu-id="7efef-192">Category</span></span>|<span data-ttu-id="7efef-193">DLP</span><span class="sxs-lookup"><span data-stu-id="7efef-193">DLP</span></span>|
|<span data-ttu-id="7efef-194">Impostazioni filtro</span><span class="sxs-lookup"><span data-stu-id="7efef-194">Filter settings</span></span>|<span data-ttu-id="7efef-195">Livello di accesso = Pubblico (Internet), Pubblico, Esterno</span><span class="sxs-lookup"><span data-stu-id="7efef-195">Access level = Public (Internet), Public, External</span></span> <p> <span data-ttu-id="7efef-196">App = \<select apps\> (utilizzare questa impostazione se si desidera limitare il monitoraggio ad app SaaS specifiche)</span><span class="sxs-lookup"><span data-stu-id="7efef-196">App = \<select apps\> (use this setting if you want to limit monitoring to specific SaaS apps)</span></span>|
|<span data-ttu-id="7efef-197">Applica a</span><span class="sxs-lookup"><span data-stu-id="7efef-197">Apply to</span></span>|<span data-ttu-id="7efef-198">Tutti i file, tutti i proprietari</span><span class="sxs-lookup"><span data-stu-id="7efef-198">All files, all owners</span></span>|
|<span data-ttu-id="7efef-199">Ispezione del contenuto</span><span class="sxs-lookup"><span data-stu-id="7efef-199">Content inspection</span></span>|<span data-ttu-id="7efef-200">Include i file che corrispondono a un'espressione presente: Tutti i paesi - Finanza: numero di carta di credito</span><span class="sxs-lookup"><span data-stu-id="7efef-200">Includes files that match a present expression: All countries: Finance: Credit card number</span></span> <p> <span data-ttu-id="7efef-201">Non richiedere il contesto rilevante: deselezionato (questa impostazione troverà una corrispondenza con parole chiave e regex)</span><span class="sxs-lookup"><span data-stu-id="7efef-201">Don't require relevant context: unchecked (this setting will match keywords as well as regex)</span></span> <p> <span data-ttu-id="7efef-202">Include file con almeno 1 corrispondenza</span><span class="sxs-lookup"><span data-stu-id="7efef-202">Includes files with at least 1 match</span></span> <p> <span data-ttu-id="7efef-203">Annulla il mascheramento degli ultimi 4 caratteri della violazione: selezionato</span><span class="sxs-lookup"><span data-stu-id="7efef-203">Unmask the last 4 characters of the violation: checked</span></span>|
|<span data-ttu-id="7efef-204">Avvisi</span><span class="sxs-lookup"><span data-stu-id="7efef-204">Alerts</span></span>|<span data-ttu-id="7efef-205">Crea un avviso per ogni file corrispondente: selezionato</span><span class="sxs-lookup"><span data-stu-id="7efef-205">Create an alert for each matching file: checked</span></span> <p> <span data-ttu-id="7efef-206">Limite di avvisi giornaliero: 1.000</span><span class="sxs-lookup"><span data-stu-id="7efef-206">Daily alert limit: 1000</span></span> <p> <span data-ttu-id="7efef-207">Seleziona un avviso come e-mail: selezionato</span><span class="sxs-lookup"><span data-stu-id="7efef-207">Select an alert as email: checked</span></span> <p> <span data-ttu-id="7efef-208">A: infosec@contoso.com</span><span class="sxs-lookup"><span data-stu-id="7efef-208">To: infosec@contoso.com</span></span>|
|<span data-ttu-id="7efef-209">Governance</span><span class="sxs-lookup"><span data-stu-id="7efef-209">Governance</span></span>|<span data-ttu-id="7efef-210">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="7efef-210">Microsoft OneDrive for Business</span></span> <p> <span data-ttu-id="7efef-211">Rendi privato: selezionare Rimuovi gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="7efef-211">Make private: check Remove External Users</span></span> <p> <span data-ttu-id="7efef-212">Tutte le altre impostazioni: deselezionato</span><span class="sxs-lookup"><span data-stu-id="7efef-212">All other settings: unchecked</span></span> <p> <span data-ttu-id="7efef-213">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7efef-213">Microsoft SharePoint Online</span></span> <p> <span data-ttu-id="7efef-214">Rendi privato: selezionare Rimuovi gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="7efef-214">Make private: check Remove External Users</span></span> <p> <span data-ttu-id="7efef-215">Tutte le altre impostazioni: deselezionato</span><span class="sxs-lookup"><span data-stu-id="7efef-215">All other settings: unchecked</span></span>|
|

<span data-ttu-id="7efef-216">Criteri simili:</span><span class="sxs-lookup"><span data-stu-id="7efef-216">Similar policies:</span></span>

- <span data-ttu-id="7efef-217">Individuare la condivisione di file contenenti informazioni personali - Indirizzo e-mail</span><span class="sxs-lookup"><span data-stu-id="7efef-217">Detect sharing of Files containing PII - Email Address</span></span>
- <span data-ttu-id="7efef-218">Individuare la condivisione di file contenenti informazioni personali - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="7efef-218">Detect sharing of Files containing PII - Passport Number</span></span>

### <a name="detect-customer-or-hr-data-in-box-or-onedrive-for-business"></a><span data-ttu-id="7efef-219">Rilevare cliente o dati sulle risorse umane in Box o OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="7efef-219">Detect Customer or HR Data in Box or OneDrive for Business</span></span>

<span data-ttu-id="7efef-220">L'avviso relativo a un file etichettato come Dati della società o Dati sulle risorse umane viene caricato su OneDrive for Business o Box.</span><span class="sxs-lookup"><span data-stu-id="7efef-220">Alert when a file labeled as Customer Data or HR Data is uploaded to OneDrive for Business or Box.</span></span>

<span data-ttu-id="7efef-221">Note:</span><span class="sxs-lookup"><span data-stu-id="7efef-221">Notes:</span></span>

- <span data-ttu-id="7efef-222">Il monitoraggio di Box richiede un connettore configurato con l'SDK API Connector.</span><span class="sxs-lookup"><span data-stu-id="7efef-222">Box monitoring requires a connector be configured using the API Connector SDK.</span></span>
- <span data-ttu-id="7efef-223">Questo criterio richiede funzionalità al momento in anteprima privata.</span><span class="sxs-lookup"><span data-stu-id="7efef-223">This policy requires capabilities that are currently in private preview.</span></span>

****

|<span data-ttu-id="7efef-224">Controllo</span><span class="sxs-lookup"><span data-stu-id="7efef-224">Control</span></span>|<span data-ttu-id="7efef-225">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="7efef-225">Settings</span></span>|
|---|---|
|<span data-ttu-id="7efef-226">Tipo di criterio</span><span class="sxs-lookup"><span data-stu-id="7efef-226">Policy type</span></span>|<span data-ttu-id="7efef-227">Criteri attività</span><span class="sxs-lookup"><span data-stu-id="7efef-227">Activity policy</span></span>|
|<span data-ttu-id="7efef-228">Modello di criteri</span><span class="sxs-lookup"><span data-stu-id="7efef-228">Policy template</span></span>|<span data-ttu-id="7efef-229">Nessun modello</span><span class="sxs-lookup"><span data-stu-id="7efef-229">No template</span></span>|
|<span data-ttu-id="7efef-230">Gravità del criterio</span><span class="sxs-lookup"><span data-stu-id="7efef-230">Policy severity</span></span>|<span data-ttu-id="7efef-231">Alta</span><span class="sxs-lookup"><span data-stu-id="7efef-231">High</span></span>|
|<span data-ttu-id="7efef-232">Categoria</span><span class="sxs-lookup"><span data-stu-id="7efef-232">Category</span></span>|<span data-ttu-id="7efef-233">Controllo della condivisione</span><span class="sxs-lookup"><span data-stu-id="7efef-233">Sharing Control</span></span>|
|<span data-ttu-id="7efef-234">Azione su</span><span class="sxs-lookup"><span data-stu-id="7efef-234">Act on</span></span>|<span data-ttu-id="7efef-235">Singola attività</span><span class="sxs-lookup"><span data-stu-id="7efef-235">Single activity</span></span>|
|<span data-ttu-id="7efef-236">Impostazioni filtro</span><span class="sxs-lookup"><span data-stu-id="7efef-236">Filter settings</span></span>|<span data-ttu-id="7efef-237">Tipo di attività = Carica file</span><span class="sxs-lookup"><span data-stu-id="7efef-237">Activity type = Upload File</span></span> <p> <span data-ttu-id="7efef-238">App = Microsoft OneDrive for Business e Box</span><span class="sxs-lookup"><span data-stu-id="7efef-238">App = Microsoft OneDrive for Business and Box</span></span> <p> <span data-ttu-id="7efef-239">Etichetta di classificazione (al momento in anteprima privata): Azure Information Protection = Dati della società, Risorse umane - Dati sulle retribuzioni, Risorse umane - Dati sui dipendenti</span><span class="sxs-lookup"><span data-stu-id="7efef-239">Classification Label (currently in private preview): Azure Information Protection = Customer Data, Human Resources—Salary Data, Human Resources—Employee Data</span></span>|
|<span data-ttu-id="7efef-240">Avvisi</span><span class="sxs-lookup"><span data-stu-id="7efef-240">Alerts</span></span>|<span data-ttu-id="7efef-241">Crea un avviso: selezionato</span><span class="sxs-lookup"><span data-stu-id="7efef-241">Create an alert: checked</span></span> <p> <span data-ttu-id="7efef-242">Limite di avvisi giornaliero: 1.000</span><span class="sxs-lookup"><span data-stu-id="7efef-242">Daily alert limit: 1000</span></span> <p> <span data-ttu-id="7efef-243">Seleziona un avviso come e-mail: selezionato</span><span class="sxs-lookup"><span data-stu-id="7efef-243">Select an alert as email: checked</span></span> <p> <span data-ttu-id="7efef-244">A: infosec@contoso.com</span><span class="sxs-lookup"><span data-stu-id="7efef-244">To: infosec@contoso.com</span></span>|
|<span data-ttu-id="7efef-245">Governance</span><span class="sxs-lookup"><span data-stu-id="7efef-245">Governance</span></span>|<span data-ttu-id="7efef-246">Tutte le app</span><span class="sxs-lookup"><span data-stu-id="7efef-246">All apps</span></span> <p> <span data-ttu-id="7efef-247">Metti utente in quarantena: selezionato</span><span class="sxs-lookup"><span data-stu-id="7efef-247">Put user in quarantine: check</span></span> <p> <span data-ttu-id="7efef-248">Tutte le altre impostazioni: deselezionato</span><span class="sxs-lookup"><span data-stu-id="7efef-248">All other settings: unchecked</span></span> <p> <span data-ttu-id="7efef-249">Office 365</span><span class="sxs-lookup"><span data-stu-id="7efef-249">Office 365</span></span> <p> <span data-ttu-id="7efef-250">Metti utente in quarantena: selezionato</span><span class="sxs-lookup"><span data-stu-id="7efef-250">Put user in quarantine: check</span></span> <p> <span data-ttu-id="7efef-251">Tutte le altre impostazioni: deselezionato</span><span class="sxs-lookup"><span data-stu-id="7efef-251">All other settings: unchecked</span></span>|
|

<span data-ttu-id="7efef-252">Criteri simili:</span><span class="sxs-lookup"><span data-stu-id="7efef-252">Similar policies:</span></span>

- <span data-ttu-id="7efef-253">Rilevare download di grandi dimensioni di dati dei clienti o dati delle risorse umane: avviso relativo al rilevamento del download di un gran numero di file contenenti dati dei clienti o sulle risorse umane da parte di un singolo utente in un breve periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="7efef-253">Detect large downloads of Customer data or HR Data—Alert when a large number of files containing customer data or HR data have been detected being downloaded by a single user within a short period of time.</span></span>
- <span data-ttu-id="7efef-254">Individuare la condivisione di dati dei clienti e delle risorse umane: avviso relativo alla condivisione di file contenenti dati sulla società o sulle risorse umane.</span><span class="sxs-lookup"><span data-stu-id="7efef-254">Detect Sharing of Customer and HR Data—Alert when files containing Customer or HR Data are shared.</span></span>