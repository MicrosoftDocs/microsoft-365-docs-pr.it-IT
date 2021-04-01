---
title: Creare regole di rilevamento personalizzate in Microsoft Defender ATP
ms.reviewer: ''
description: Informazioni su come creare regole di rilevamento personalizzate basate su query di ricerca avanzate
keywords: rilevamenti personalizzati, creare, gestire, avvisi, modificare, eseguire su richiesta, frequenza, intervallo, regole di rilevamento, ricerca avanzata, ricerca, query, azioni di risposta, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 48b1f1bf9506acc8491887fca49295d5e4ccbd69
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382710"
---
# <a name="create-custom-detection-rules"></a><span data-ttu-id="9cafe-104">Creare regole di rilevamento personalizzate</span><span class="sxs-lookup"><span data-stu-id="9cafe-104">Create custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9cafe-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="9cafe-105">**Applies to:**</span></span>
- [<span data-ttu-id="9cafe-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="9cafe-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9cafe-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9cafe-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="9cafe-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="9cafe-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9cafe-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="9cafe-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="9cafe-110">Le regole di rilevamento personalizzate create da query [di](advanced-hunting-overview.md) ricerca avanzate consentono di monitorare in modo proattivo diversi eventi e stati di sistema, tra cui attività sospette di violazione e dispositivi non configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="9cafe-110">Custom detection rules built from [advanced hunting](advanced-hunting-overview.md) queries let you proactively monitor various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="9cafe-111">Puoi impostarli per l'esecuzione a intervalli regolari, generando avvisi ed eseguire azioni di risposta ogni volta che ci sono corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="9cafe-111">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="9cafe-112">Leggere questo articolo per informazioni su come creare nuove regole di rilevamento personalizzate.</span><span class="sxs-lookup"><span data-stu-id="9cafe-112">Read this article to learn how to create new custom detection rules.</span></span> <span data-ttu-id="9cafe-113">In [altri, vedere Visualizzazione e gestione delle regole esistenti.](custom-detections-manage.md)</span><span class="sxs-lookup"><span data-stu-id="9cafe-113">Or [see viewing and managing existing rules](custom-detections-manage.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9cafe-114">Per creare o gestire rilevamenti personalizzati, [il ruolo](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) deve disporre dell'autorizzazione gestisci **impostazioni di** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9cafe-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="1-prepare-the-query"></a><span data-ttu-id="9cafe-115">1. Preparare la query.</span><span class="sxs-lookup"><span data-stu-id="9cafe-115">1. Prepare the query.</span></span>

<span data-ttu-id="9cafe-116">In Microsoft Defender Security Center passare a **Ricerca avanzata** e selezionare una query esistente o creare una nuova query.</span><span class="sxs-lookup"><span data-stu-id="9cafe-116">In Microsoft Defender Security Center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="9cafe-117">Quando si utilizza una nuova query, eseguire la query per identificare gli errori e comprendere i possibili risultati.</span><span class="sxs-lookup"><span data-stu-id="9cafe-117">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="9cafe-118">Per impedire al servizio di restituire troppi avvisi, ogni regola può generare solo 100 avvisi ogni volta che viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="9cafe-118">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="9cafe-119">Prima di creare una regola, modificare la query per evitare avvisi per le normali attività quotidiane.</span><span class="sxs-lookup"><span data-stu-id="9cafe-119">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>

### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="9cafe-120">Colonne obbligatorie nei risultati della query</span><span class="sxs-lookup"><span data-stu-id="9cafe-120">Required columns in the query results</span></span>

<span data-ttu-id="9cafe-121">Per utilizzare una query per una regola di rilevamento personalizzata, la query deve restituire le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="9cafe-121">To use a query for a custom detection rule, the query must return the following columns:</span></span>

- `Timestamp`
- `DeviceId`
- `ReportId`

<span data-ttu-id="9cafe-122">Le query semplici, ad esempio quelle che non utilizzano l'operatore or per personalizzare o aggregare i risultati, in genere `project` `summarize` restituiscono queste colonne comuni.</span><span class="sxs-lookup"><span data-stu-id="9cafe-122">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="9cafe-123">Esistono diversi modi per garantire che query più complesse restituiranno queste colonne.</span><span class="sxs-lookup"><span data-stu-id="9cafe-123">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="9cafe-124">Ad esempio, se preferisci aggregare e contare per , puoi comunque restituirli e riceverli `DeviceId` dall'evento più recente che coinvolge ogni `Timestamp` `ReportId` dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9cafe-124">For example, if you prefer to aggregate and count by `DeviceId`, you can still return `Timestamp` and `ReportId` by getting them from the most recent event involving each device.</span></span>

<span data-ttu-id="9cafe-125">La query di esempio seguente conta il numero di dispositivi univoci ( ) con rilevamenti antivirus e lo usa per trovare solo i dispositivi con più `DeviceId` di cinque rilevamenti.</span><span class="sxs-lookup"><span data-stu-id="9cafe-125">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this to find only those devices with more than five detections.</span></span> <span data-ttu-id="9cafe-126">Per restituire l'ultimo `Timestamp` e il corrispondente , viene utilizzato `ReportId` `summarize` l'operatore con la funzione `arg_max` .</span><span class="sxs-lookup"><span data-stu-id="9cafe-126">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="9cafe-127">Per migliorare le prestazioni delle query, impostare un filtro temporale che corrisponda alla frequenza di esecuzione prevista per la regola.</span><span class="sxs-lookup"><span data-stu-id="9cafe-127">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="9cafe-128">Poiché l'esecuzione meno frequente è ogni 24 ore, il filtro per il giorno precedente copre tutti i nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="9cafe-128">Since the least frequent run is every 24 hours, filtering for the past day will cover all new data.</span></span>

## <a name="2-create-a-new-rule-and-provide-alert-details"></a><span data-ttu-id="9cafe-129">2. Creare una nuova regola e fornire i dettagli dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="9cafe-129">2. Create a new rule and provide alert details.</span></span>

<span data-ttu-id="9cafe-130">Con la query nell'editor di query, selezionare Crea regola **di rilevamento** e specificare i dettagli dell'avviso seguenti:</span><span class="sxs-lookup"><span data-stu-id="9cafe-130">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="9cafe-131">**Nome rilevamento**- Nome della regola di rilevamento</span><span class="sxs-lookup"><span data-stu-id="9cafe-131">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="9cafe-132">**Frequenza:** intervallo per l'esecuzione della query e l'esecuzione di azioni.</span><span class="sxs-lookup"><span data-stu-id="9cafe-132">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="9cafe-133">Vedi ulteriori indicazioni di seguito</span><span class="sxs-lookup"><span data-stu-id="9cafe-133">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="9cafe-134">**Titolo dell'avviso**: titolo visualizzato con gli avvisi attivati dalla regola</span><span class="sxs-lookup"><span data-stu-id="9cafe-134">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="9cafe-135">**Gravità:** potenziale rischio del componente o dell'attività identificato dalla regola.</span><span class="sxs-lookup"><span data-stu-id="9cafe-135">**Severity**—potential risk of the component or activity identified by the rule.</span></span> [<span data-ttu-id="9cafe-136">Informazioni sulla gravità degli avvisi</span><span class="sxs-lookup"><span data-stu-id="9cafe-136">Read about alert severities</span></span>](alerts-queue.md#severity)
- <span data-ttu-id="9cafe-137">**Categoria:** tipo di componente o attività di minaccia, se presente.</span><span class="sxs-lookup"><span data-stu-id="9cafe-137">**Category**—type of threat component or activity, if any.</span></span> [<span data-ttu-id="9cafe-138">Informazioni sulle categorie di avvisi</span><span class="sxs-lookup"><span data-stu-id="9cafe-138">Read about alert categories</span></span>](alerts-queue.md#understanding-alert-categories)
- <span data-ttu-id="9cafe-139">**MITRE ATT&CK,** ovvero una o più tecniche di attacco identificate dalla regola, come documentato nel framework MITRE ATT&CK.</span><span class="sxs-lookup"><span data-stu-id="9cafe-139">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the MITRE ATT&CK framework.</span></span> <span data-ttu-id="9cafe-140">Questa sezione non è disponibile con determinate categorie di avviso, ad esempio malware, ransomware, attività sospette e software indesiderato</span><span class="sxs-lookup"><span data-stu-id="9cafe-140">This section is not available with certain alert categories, such as malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="9cafe-141">**Descrizione:** ulteriori informazioni sul componente o sull'attività identificate dalla regola</span><span class="sxs-lookup"><span data-stu-id="9cafe-141">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="9cafe-142">**Azioni consigliate:** azioni aggiuntive che i risponditori potrebbero intraprendere in risposta a un avviso</span><span class="sxs-lookup"><span data-stu-id="9cafe-142">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

<span data-ttu-id="9cafe-143">Per ulteriori informazioni sulla modalità di visualizzazione dei dettagli dell'avviso, [vedere informazioni sulla coda degli avvisi.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="9cafe-143">For more information about how alert details are displayed, [read about the alert queue](alerts-queue.md).</span></span>

### <a name="rule-frequency"></a><span data-ttu-id="9cafe-144">Frequenza delle regole</span><span class="sxs-lookup"><span data-stu-id="9cafe-144">Rule frequency</span></span>

<span data-ttu-id="9cafe-145">Quando viene salvata, viene eseguita immediatamente una nuova regola di rilevamento personalizzata e viene verificata la presenza di corrispondenze degli ultimi 30 giorni di dati.</span><span class="sxs-lookup"><span data-stu-id="9cafe-145">When saved, a new custom detection rule immediately runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="9cafe-146">La regola viene quindi rieseguiti a intervalli fissi e durate di lookback in base alla frequenza scelta:</span><span class="sxs-lookup"><span data-stu-id="9cafe-146">The rule then runs again at fixed intervals and lookback durations based on the frequency you choose:</span></span>

- <span data-ttu-id="9cafe-147">**Ogni 24 ore:** viene eseguito ogni 24 ore, controllando i dati degli ultimi 30 giorni</span><span class="sxs-lookup"><span data-stu-id="9cafe-147">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="9cafe-148">**Ogni 12 ore:** viene eseguito ogni 12 ore, controllando i dati delle ultime 24 ore</span><span class="sxs-lookup"><span data-stu-id="9cafe-148">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="9cafe-149">**Ogni 3 ore:** viene eseguito ogni 3 ore, controllando i dati delle ultime 6 ore</span><span class="sxs-lookup"><span data-stu-id="9cafe-149">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="9cafe-150">**Ogni ora:** viene eseguito ogni ora, controllando i dati delle ultime 2 ore</span><span class="sxs-lookup"><span data-stu-id="9cafe-150">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

<span data-ttu-id="9cafe-151">Quando si modifica una regola, questa verrà eseguita con le modifiche applicate nella successiva fase di esecuzione pianificata in base alla frequenza impostata.</span><span class="sxs-lookup"><span data-stu-id="9cafe-151">When you edit a rule, it will run with the applied changes in the next run time scheduled according to the frequency you set.</span></span>


> [!TIP]
> <span data-ttu-id="9cafe-152">Associare i filtri tempo nella query alla durata del lookback.</span><span class="sxs-lookup"><span data-stu-id="9cafe-152">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="9cafe-153">I risultati al di fuori della durata del lookback vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="9cafe-153">Results outside of the lookback duration are ignored.</span></span>

<span data-ttu-id="9cafe-154">Selezionare la frequenza che corrisponde alla frequenza con cui si desidera monitorare i rilevamenti e considerare la capacità dell'organizzazione di rispondere agli avvisi.</span><span class="sxs-lookup"><span data-stu-id="9cafe-154">Select the frequency that matches how closely you want to monitor detections, and consider your organization's capacity to respond to the alerts.</span></span>

## <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="9cafe-155">3. Scegliere le entità influenzate.</span><span class="sxs-lookup"><span data-stu-id="9cafe-155">3. Choose the impacted entities.</span></span>

<span data-ttu-id="9cafe-156">Identificare le colonne nei risultati della query in cui si prevede di trovare l'entità principale interessata o interessata.</span><span class="sxs-lookup"><span data-stu-id="9cafe-156">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="9cafe-157">Ad esempio, una query potrebbe restituire sia gli ID dispositivo che gli ID utente.</span><span class="sxs-lookup"><span data-stu-id="9cafe-157">For example, a query might return both device and user IDs.</span></span> <span data-ttu-id="9cafe-158">L'identificazione di quale di queste colonne rappresenta l'entità principale influenzata consente al servizio di aggregare avvisi rilevanti, correlare eventi imprevisti e azioni di risposta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="9cafe-158">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="9cafe-159">È possibile selezionare una sola colonna per ogni tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="9cafe-159">You can select only one column for each entity type.</span></span> <span data-ttu-id="9cafe-160">Le colonne non restituite dalla query non possono essere selezionate.</span><span class="sxs-lookup"><span data-stu-id="9cafe-160">Columns that are not returned by your query can't be selected.</span></span>

## <a name="4-specify-actions"></a><span data-ttu-id="9cafe-161">4. Specificare le azioni.</span><span class="sxs-lookup"><span data-stu-id="9cafe-161">4. Specify actions.</span></span>

<span data-ttu-id="9cafe-162">La regola di rilevamento personalizzata può eseguire automaticamente azioni su file o dispositivi restituiti dalla query.</span><span class="sxs-lookup"><span data-stu-id="9cafe-162">Your custom detection rule can automatically take actions on files or devices that are returned by the query.</span></span>

### <a name="actions-on-devices"></a><span data-ttu-id="9cafe-163">Azioni nei dispositivi</span><span class="sxs-lookup"><span data-stu-id="9cafe-163">Actions on devices</span></span>

<span data-ttu-id="9cafe-164">Queste azioni vengono applicate ai dispositivi nella `DeviceId` colonna dei risultati della query:</span><span class="sxs-lookup"><span data-stu-id="9cafe-164">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>

- <span data-ttu-id="9cafe-165">**Isola dispositivo:** applica l'isolamento di rete completo, impedendo al dispositivo di connettersi a qualsiasi applicazione o servizio, ad eccezione del servizio Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="9cafe-165">**Isolate device**—applies full network isolation, preventing the device from connecting to any application or service, except for the Defender for Endpoint service.</span></span> [<span data-ttu-id="9cafe-166">Altre informazioni sull'isolamento dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="9cafe-166">Learn more about device isolation</span></span>](respond-machine-alerts.md#isolate-devices-from-the-network)
- <span data-ttu-id="9cafe-167">**Raccogli pacchetto di analisi:** raccoglie le informazioni sul dispositivo in un file ZIP.</span><span class="sxs-lookup"><span data-stu-id="9cafe-167">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="9cafe-168">Altre informazioni sul pacchetto di analisi</span><span class="sxs-lookup"><span data-stu-id="9cafe-168">Learn more about the investigation package</span></span>](respond-machine-alerts.md#collect-investigation-package-from-devices)
- <span data-ttu-id="9cafe-169">**Esegui analisi antivirus:** esegue un'analisi completa di Microsoft Defender Antivirus nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="9cafe-169">**Run antivirus scan**—performs a full Microsoft Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="9cafe-170">**Avvia indagine:** avvia [un'indagine](automated-investigations.md) automatizzata nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="9cafe-170">**Initiate investigation**—starts an [automated investigation](automated-investigations.md) on the device</span></span>
- <span data-ttu-id="9cafe-171">**Limita l'esecuzione** dell'app: imposta le restrizioni sul dispositivo per consentire l'esecuzione solo dei file firmati con un certificato rilasciato da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9cafe-171">**Restrict app execution**—sets restrictions on the device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="9cafe-172">Altre informazioni sulla limitazione dell'esecuzione delle app</span><span class="sxs-lookup"><span data-stu-id="9cafe-172">Learn more about restricting app execution</span></span>](respond-machine-alerts.md#restrict-app-execution)

### <a name="actions-on-files"></a><span data-ttu-id="9cafe-173">Azioni sui file</span><span class="sxs-lookup"><span data-stu-id="9cafe-173">Actions on files</span></span>

<span data-ttu-id="9cafe-174">Queste azioni vengono applicate ai file nella colonna o nei `SHA1` `InitiatingProcessSHA1` risultati della query:</span><span class="sxs-lookup"><span data-stu-id="9cafe-174">These actions are applied to files in the `SHA1` or the `InitiatingProcessSHA1` column of the query results:</span></span>

- <span data-ttu-id="9cafe-175">**Consenti/Blocca:** aggiunge automaticamente il file [all'elenco](manage-indicators.md) di indicatori personalizzati in modo che sia sempre consentita l'esecuzione o il blocco dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9cafe-175">**Allow/Block**—automatically adds the file to your [custom indicator list](manage-indicators.md) so that it is always allowed to run or blocked from running.</span></span> <span data-ttu-id="9cafe-176">Puoi impostare l'ambito di questa azione in modo che sia eseguita solo nei gruppi di dispositivi selezionati.</span><span class="sxs-lookup"><span data-stu-id="9cafe-176">You can set the scope of this action so that it is taken only on selected device groups.</span></span> <span data-ttu-id="9cafe-177">Questo ambito è indipendente dall'ambito della regola.</span><span class="sxs-lookup"><span data-stu-id="9cafe-177">This scope is independent of the scope of the rule.</span></span>
- <span data-ttu-id="9cafe-178">**File in** quarantena: elimina il file dalla posizione corrente e ne inserisce una copia in quarantena</span><span class="sxs-lookup"><span data-stu-id="9cafe-178">**Quarantine file**—deletes the file from its current location and places a copy in quarantine</span></span>

### <a name="actions-on-users"></a><span data-ttu-id="9cafe-179">Azioni sugli utenti</span><span class="sxs-lookup"><span data-stu-id="9cafe-179">Actions on users</span></span>

- <span data-ttu-id="9cafe-180">**Contrassegna l'utente come** compromesso: imposta il livello di rischio dell'utente su "alto" in Azure Active Directory, attivando i criteri [di protezione delle identità corrispondenti.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels)</span><span class="sxs-lookup"><span data-stu-id="9cafe-180">**Mark user as compromised**—sets the user's risk level to "high" in Azure Active Directory, triggering the corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels).</span></span>

## <a name="5-set-the-rule-scope"></a><span data-ttu-id="9cafe-181">5. Impostare l'ambito della regola.</span><span class="sxs-lookup"><span data-stu-id="9cafe-181">5. Set the rule scope.</span></span>

<span data-ttu-id="9cafe-182">Impostare l'ambito per specificare quali dispositivi sono coperti dalla regola:</span><span class="sxs-lookup"><span data-stu-id="9cafe-182">Set the scope to specify which devices are covered by the rule:</span></span>

- <span data-ttu-id="9cafe-183">Tutti i dispositivi</span><span class="sxs-lookup"><span data-stu-id="9cafe-183">All devices</span></span>
- <span data-ttu-id="9cafe-184">Gruppi di dispositivi specifici</span><span class="sxs-lookup"><span data-stu-id="9cafe-184">Specific device groups</span></span>

<span data-ttu-id="9cafe-185">Verranno interrogati solo i dati dei dispositivi nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="9cafe-185">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="9cafe-186">Inoltre, le azioni verranno eseguite solo su tali dispositivi.</span><span class="sxs-lookup"><span data-stu-id="9cafe-186">Also, actions will be taken only on those devices.</span></span>

## <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="9cafe-187">6. Esaminare e attivare la regola.</span><span class="sxs-lookup"><span data-stu-id="9cafe-187">6. Review and turn on the rule.</span></span>

<span data-ttu-id="9cafe-188">Dopo aver esaminato la regola, selezionare **Crea** per salvarla.</span><span class="sxs-lookup"><span data-stu-id="9cafe-188">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="9cafe-189">La regola di rilevamento personalizzata viene eseguita immediatamente.</span><span class="sxs-lookup"><span data-stu-id="9cafe-189">The custom detection rule immediately runs.</span></span> <span data-ttu-id="9cafe-190">Viene eseguito di nuovo in base alla frequenza configurata per verificare la presenza di corrispondenze, generare avvisi ed eseguire azioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="9cafe-190">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

<span data-ttu-id="9cafe-191">È possibile [visualizzare e gestire regole di rilevamento personalizzate,](custom-detections-manage.md)controllare le esecuzioni precedenti ed esaminare gli avvisi che hanno attivato.</span><span class="sxs-lookup"><span data-stu-id="9cafe-191">You can [view and manage custom detection rules](custom-detections-manage.md), check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="9cafe-192">È inoltre possibile eseguire una regola su richiesta e modificarla.</span><span class="sxs-lookup"><span data-stu-id="9cafe-192">You can also run a rule on demand and modify it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9cafe-193">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9cafe-193">Related topics</span></span>

- [<span data-ttu-id="9cafe-194">Visualizzare e gestire regole di rilevamento personalizzate</span><span class="sxs-lookup"><span data-stu-id="9cafe-194">View and manage custom detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="9cafe-195">Panoramica dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="9cafe-195">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="9cafe-196">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="9cafe-196">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9cafe-197">Scoprire il linguaggio delle query in Ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="9cafe-197">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9cafe-198">Visualizzare e organizzare gli avvisi</span><span class="sxs-lookup"><span data-stu-id="9cafe-198">View and organize alerts</span></span>](alerts-queue.md)