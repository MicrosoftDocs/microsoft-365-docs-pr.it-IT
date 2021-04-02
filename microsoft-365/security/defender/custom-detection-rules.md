---
title: Creare e gestire regole di rilevamento personalizzate in Microsoft 365 Defender
description: Informazioni su come creare e gestire regole di rilevamento personalizzate basate su query di ricerca avanzate
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, rilevamenti personalizzati, regole, schema, kusto, Microsoft 365, Microsoft Threat Protection, RBAC, autorizzazioni, Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 220e4e6546899dd00f3a02bf83039a928be4f8dc
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498842"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="9b531-104">Creare e gestire regole di rilevamento personalizzate</span><span class="sxs-lookup"><span data-stu-id="9b531-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9b531-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="9b531-105">**Applies to:**</span></span>
- <span data-ttu-id="9b531-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b531-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9b531-107">Le regole di rilevamento personalizzate sono regole che è possibile progettare e modificare utilizzando [query di ricerca](advanced-hunting-overview.md) avanzate.</span><span class="sxs-lookup"><span data-stu-id="9b531-107">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="9b531-108">Queste regole consentono di monitorare in modo proattivo vari eventi e stati di sistema, tra cui attività di violazione sospetta e endpoint non configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="9b531-108">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="9b531-109">Puoi impostarli per l'esecuzione a intervalli regolari, generando avvisi ed eseguire azioni di risposta ogni volta che ci sono corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="9b531-109">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="9b531-110">Autorizzazioni necessarie per la gestione dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="9b531-110">Required permissions for managing custom detections</span></span>

<span data-ttu-id="9b531-111">Per gestire i rilevamenti personalizzati, è necessario disporre di uno di questi ruoli:</span><span class="sxs-lookup"><span data-stu-id="9b531-111">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="9b531-112">**Amministratore della** sicurezza: gli utenti con questo [ruolo di Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) possono gestire le impostazioni di sicurezza nel Centro sicurezza Microsoft 365 e in altri portali e servizi.</span><span class="sxs-lookup"><span data-stu-id="9b531-112">**Security administrator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="9b531-113">**Operatore di** sicurezza: gli utenti con questo ruolo [di Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) possono gestire gli avvisi e avere accesso globale in sola lettura alle funzionalità correlate alla sicurezza, incluse tutte le informazioni nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9b531-113">**Security operator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="9b531-114">Questo ruolo è sufficiente per gestire i rilevamenti personalizzati solo se il controllo di accesso basato sui ruoli (RBAC) è disattivato in Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="9b531-114">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="9b531-115">Se è stato configurato RBAC, è necessario disporre anche dell'autorizzazione di gestione delle impostazioni **di** sicurezza per Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="9b531-115">If you have RBAC configured, you also need the **manage security settings** permission for Defender for Endpoint.</span></span>

<span data-ttu-id="9b531-116">Per gestire le autorizzazioni necessarie, un **amministratore globale** può:</span><span class="sxs-lookup"><span data-stu-id="9b531-116">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="9b531-117">Assegnare **il ruolo di amministratore della** sicurezza o **operatore** di sicurezza nell'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com/) in **Ruoli**  >  **Amministratore sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="9b531-117">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="9b531-118">Controllare le impostazioni RBAC per Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) in **Impostazioni**  >  **Autorizzazioni**  >  **Ruoli**.</span><span class="sxs-lookup"><span data-stu-id="9b531-118">Check RBAC settings for Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="9b531-119">Selezionare il ruolo corrispondente per assegnare **l'autorizzazione gestisci impostazioni di** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9b531-119">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="9b531-120">Per gestire i rilevamenti **personalizzati,** gli operatori della sicurezza dovranno disporre dell'autorizzazione di gestione delle impostazioni di sicurezza in Microsoft Defender per Endpoint se RBAC è attivato. </span><span class="sxs-lookup"><span data-stu-id="9b531-120">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender for Endpoint if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="9b531-121">Creare una regola di rilevamento personalizzata</span><span class="sxs-lookup"><span data-stu-id="9b531-121">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="9b531-122">1. Preparare la query.</span><span class="sxs-lookup"><span data-stu-id="9b531-122">1. Prepare the query.</span></span>

<span data-ttu-id="9b531-123">Nel Centro sicurezza Microsoft 365 passare a Ricerca **avanzata** e selezionare una query esistente o creare una nuova query.</span><span class="sxs-lookup"><span data-stu-id="9b531-123">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="9b531-124">Quando si utilizza una nuova query, eseguire la query per identificare gli errori e comprendere i possibili risultati.</span><span class="sxs-lookup"><span data-stu-id="9b531-124">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="9b531-125">Per impedire al servizio di restituire troppi avvisi, ogni regola può generare solo 100 avvisi ogni volta che viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="9b531-125">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="9b531-126">Prima di creare una regola, modificare la query per evitare avvisi per le normali attività quotidiane.</span><span class="sxs-lookup"><span data-stu-id="9b531-126">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="9b531-127">Colonne obbligatorie nei risultati della query</span><span class="sxs-lookup"><span data-stu-id="9b531-127">Required columns in the query results</span></span>
<span data-ttu-id="9b531-128">Per creare una regola di rilevamento personalizzata, la query deve restituire le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b531-128">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="9b531-129">`Timestamp`: utilizzato per impostare il timestamp per gli avvisi generati</span><span class="sxs-lookup"><span data-stu-id="9b531-129">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="9b531-130">`ReportId`: abilita le ricerche per i record originali</span><span class="sxs-lookup"><span data-stu-id="9b531-130">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="9b531-131">Una delle colonne seguenti che identificano dispositivi, utenti o cassette postali specifici:</span><span class="sxs-lookup"><span data-stu-id="9b531-131">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="9b531-132">`SenderFromAddress` (mittente della busta o indirizzo Return-Path destinatario)</span><span class="sxs-lookup"><span data-stu-id="9b531-132">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="9b531-133">`SenderMailFromAddress` (indirizzo del mittente visualizzato dal client di posta elettronica)</span><span class="sxs-lookup"><span data-stu-id="9b531-133">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="9b531-134">Il supporto per altre entità verrà aggiunto quando vengono aggiunte nuove tabelle allo [schema di ricerca avanzata.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="9b531-134">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="9b531-135">Le query semplici, ad esempio quelle che non utilizzano l'operatore or per personalizzare o aggregare i risultati, in genere `project` `summarize` restituiscono queste colonne comuni.</span><span class="sxs-lookup"><span data-stu-id="9b531-135">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="9b531-136">Esistono diversi modi per garantire che query più complesse restituiranno queste colonne.</span><span class="sxs-lookup"><span data-stu-id="9b531-136">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="9b531-137">Ad esempio, se si preferisce aggregare e contare per entità in una colonna come , è comunque possibile restituire e ottenere dall'evento più recente che coinvolge `DeviceId` `Timestamp` ogni `ReportId` univoco `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="9b531-137">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="9b531-138">La query di esempio seguente conta il numero di dispositivi univoci ( ) con rilevamenti antivirus e usa questo conteggio per trovare solo i dispositivi con più `DeviceId` di cinque rilevamenti.</span><span class="sxs-lookup"><span data-stu-id="9b531-138">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="9b531-139">Per restituire l'ultimo `Timestamp` e il corrispondente , viene utilizzato `ReportId` `summarize` l'operatore con la funzione `arg_max` .</span><span class="sxs-lookup"><span data-stu-id="9b531-139">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="9b531-140">Per migliorare le prestazioni delle query, impostare un filtro temporale che corrisponda alla frequenza di esecuzione prevista per la regola.</span><span class="sxs-lookup"><span data-stu-id="9b531-140">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="9b531-141">Poiché l'esecuzione meno frequente _è ogni 24 ore,_ il filtro per il giorno precedente copre tutti i nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="9b531-141">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="9b531-142">2. Creare una nuova regola e fornire i dettagli dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="9b531-142">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="9b531-143">Con la query nell'editor di query, selezionare Crea regola **di rilevamento** e specificare i dettagli dell'avviso seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b531-143">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="9b531-144">**Nome rilevamento**- Nome della regola di rilevamento</span><span class="sxs-lookup"><span data-stu-id="9b531-144">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="9b531-145">**Frequenza:** intervallo per l'esecuzione della query e l'esecuzione di azioni.</span><span class="sxs-lookup"><span data-stu-id="9b531-145">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="9b531-146">Vedi ulteriori indicazioni di seguito</span><span class="sxs-lookup"><span data-stu-id="9b531-146">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="9b531-147">**Titolo dell'avviso**: titolo visualizzato con gli avvisi attivati dalla regola</span><span class="sxs-lookup"><span data-stu-id="9b531-147">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="9b531-148">**Gravità:** potenziale rischio del componente o dell'attività identificata dalla regola</span><span class="sxs-lookup"><span data-stu-id="9b531-148">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="9b531-149">**Categoria:** componente di minaccia o attività identificata dalla regola</span><span class="sxs-lookup"><span data-stu-id="9b531-149">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="9b531-150">**MITRE ATT&tecniche CK,** ovvero una o più tecniche di attacco identificate dalla regola, come documentato nel [framework MITRE ATT&CK.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="9b531-150">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="9b531-151">Questa sezione è nascosta per determinate categorie di avvisi, tra cui malware, ransomware, attività sospette e software indesiderato</span><span class="sxs-lookup"><span data-stu-id="9b531-151">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="9b531-152">**Descrizione:** ulteriori informazioni sul componente o sull'attività identificate dalla regola</span><span class="sxs-lookup"><span data-stu-id="9b531-152">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="9b531-153">**Azioni consigliate:** azioni aggiuntive che i risponditori potrebbero intraprendere in risposta a un avviso</span><span class="sxs-lookup"><span data-stu-id="9b531-153">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="9b531-154">Frequenza delle regole</span><span class="sxs-lookup"><span data-stu-id="9b531-154">Rule frequency</span></span>
<span data-ttu-id="9b531-155">Quando si salva una nuova regola, viene eseguita e viene verificata la presenza di corrispondenze degli ultimi 30 giorni di dati.</span><span class="sxs-lookup"><span data-stu-id="9b531-155">When you save a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="9b531-156">La regola viene quindi eseguita di nuovo a intervalli fissi, applicando una durata di lookback in base alla frequenza scelta:</span><span class="sxs-lookup"><span data-stu-id="9b531-156">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="9b531-157">**Ogni 24 ore:** viene eseguito ogni 24 ore, controllando i dati degli ultimi 30 giorni</span><span class="sxs-lookup"><span data-stu-id="9b531-157">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="9b531-158">**Ogni 12 ore:** viene eseguito ogni 12 ore, controllando i dati delle ultime 24 ore</span><span class="sxs-lookup"><span data-stu-id="9b531-158">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="9b531-159">**Ogni 3 ore:** viene eseguito ogni 3 ore, controllando i dati delle ultime 6 ore</span><span class="sxs-lookup"><span data-stu-id="9b531-159">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="9b531-160">**Ogni ora:** viene eseguito ogni ora, controllando i dati delle ultime 2 ore</span><span class="sxs-lookup"><span data-stu-id="9b531-160">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

<span data-ttu-id="9b531-161">Quando si modifica una regola, questa verrà eseguita con le modifiche applicate nella successiva fase di esecuzione pianificata in base alla frequenza impostata.</span><span class="sxs-lookup"><span data-stu-id="9b531-161">When you edit a rule, it will run with the applied changes in the next run time scheduled according to the frequency you set.</span></span>



>[!TIP]
> <span data-ttu-id="9b531-162">Associare i filtri tempo nella query alla durata del lookback.</span><span class="sxs-lookup"><span data-stu-id="9b531-162">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="9b531-163">I risultati al di fuori della durata del lookback vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="9b531-163">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="9b531-164">Selezionare la frequenza corrispondente alla frequenza con cui si desidera monitorare i rilevamenti.</span><span class="sxs-lookup"><span data-stu-id="9b531-164">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="9b531-165">Considerare la capacità dell'organizzazione di rispondere agli avvisi.</span><span class="sxs-lookup"><span data-stu-id="9b531-165">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="9b531-166">3. Scegliere le entità influenzate.</span><span class="sxs-lookup"><span data-stu-id="9b531-166">3. Choose the impacted entities.</span></span>
<span data-ttu-id="9b531-167">Identificare le colonne nei risultati della query in cui si prevede di trovare l'entità principale interessata o interessata.</span><span class="sxs-lookup"><span data-stu-id="9b531-167">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="9b531-168">Ad esempio, una query potrebbe restituire gli indirizzi del mittente ( `SenderFromAddress` o ) e del `SenderMailFromAddress` destinatario ( `RecipientEmailAddress` ).</span><span class="sxs-lookup"><span data-stu-id="9b531-168">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="9b531-169">L'identificazione di quale di queste colonne rappresenta l'entità principale influenzata consente al servizio di aggregare avvisi rilevanti, correlare eventi imprevisti e azioni di risposta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="9b531-169">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="9b531-170">È possibile selezionare una sola colonna per ogni tipo di entità (cassetta postale, utente o dispositivo).</span><span class="sxs-lookup"><span data-stu-id="9b531-170">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="9b531-171">Le colonne non restituite dalla query non possono essere selezionate.</span><span class="sxs-lookup"><span data-stu-id="9b531-171">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="9b531-172">4. Specificare le azioni.</span><span class="sxs-lookup"><span data-stu-id="9b531-172">4. Specify actions.</span></span>
<span data-ttu-id="9b531-173">La regola di rilevamento personalizzata può eseguire automaticamente azioni su dispositivi, file o utenti restituiti dalla query.</span><span class="sxs-lookup"><span data-stu-id="9b531-173">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="9b531-174">Azioni nei dispositivi</span><span class="sxs-lookup"><span data-stu-id="9b531-174">Actions on devices</span></span>
<span data-ttu-id="9b531-175">Queste azioni vengono applicate ai dispositivi nella `DeviceId` colonna dei risultati della query:</span><span class="sxs-lookup"><span data-stu-id="9b531-175">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="9b531-176">**Isola dispositivo:** usa Microsoft Defender for Endpoint per applicare l'isolamento di rete completo, impedendo al dispositivo di connettersi a qualsiasi applicazione o servizio.</span><span class="sxs-lookup"><span data-stu-id="9b531-176">**Isolate device**—uses Microsoft Defender for Endpoint to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="9b531-177">Altre informazioni sull'isolamento del computer di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9b531-177">Learn more about Microsoft Defender for Endpoint machine isolation</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="9b531-178">**Raccogli pacchetto di analisi:** raccoglie le informazioni sul dispositivo in un file ZIP.</span><span class="sxs-lookup"><span data-stu-id="9b531-178">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="9b531-179">Altre informazioni sul pacchetto di analisi di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9b531-179">Learn more about the Microsoft Defender for Endpoint investigation package</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="9b531-180">**Esegui analisi antivirus:** esegue un'Windows Defender antivirus completa nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="9b531-180">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="9b531-181">**Avvia un'indagine:** avvia [un'indagine](m365d-autoir.md) automatizzata sul dispositivo</span><span class="sxs-lookup"><span data-stu-id="9b531-181">**Initiate investigation**—initiates an [automated investigation](m365d-autoir.md) on the device</span></span>
- <span data-ttu-id="9b531-182">**Limita l'esecuzione dell'app:** imposta le restrizioni sul dispositivo per consentire l'esecuzione solo dei file firmati con un certificato rilasciato da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9b531-182">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="9b531-183">Altre informazioni sulle restrizioni per le app con Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9b531-183">Learn more about app restrictions with Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="9b531-184">Azioni sui file</span><span class="sxs-lookup"><span data-stu-id="9b531-184">Actions on files</span></span>
<span data-ttu-id="9b531-185">Se selezionata, è possibile scegliere di applicare l'azione Quarantena **file** ai file nella `SHA1` colonna , , o dei risultati della `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` query.</span><span class="sxs-lookup"><span data-stu-id="9b531-185">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="9b531-186">Questa azione elimina il file dal percorso corrente e ne mette una copia in quarantena.</span><span class="sxs-lookup"><span data-stu-id="9b531-186">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="9b531-187">Azioni sugli utenti</span><span class="sxs-lookup"><span data-stu-id="9b531-187">Actions on users</span></span>
<span data-ttu-id="9b531-188">Se selezionata, **l'azione** Contrassegna l'utente come compromessa viene eseguita sugli utenti nella `AccountObjectId` colonna , o dei risultati della `InitiatingProcessAccountObjectId` `RecipientObjectId` query.</span><span class="sxs-lookup"><span data-stu-id="9b531-188">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="9b531-189">Questa azione imposta il livello di rischio degli utenti su "alto" in Azure Active Directory, attivando i criteri [di protezione delle identità corrispondenti.](/azure/active-directory/identity-protection/overview-identity-protection)</span><span class="sxs-lookup"><span data-stu-id="9b531-189">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="9b531-190">L'azione consenti o blocca per le regole di rilevamento personalizzate non è attualmente supportata in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9b531-190">The allow or block action for custom detection rules is currently not supported on Microsoft 365 Defender.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="9b531-191">5. Impostare l'ambito della regola.</span><span class="sxs-lookup"><span data-stu-id="9b531-191">5. Set the rule scope.</span></span>
<span data-ttu-id="9b531-192">Impostare l'ambito per specificare quali dispositivi sono coperti dalla regola.</span><span class="sxs-lookup"><span data-stu-id="9b531-192">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="9b531-193">L'ambito influenza le regole che controllano i dispositivi e non influisce sulle regole che controllano solo le cassette postali, gli account utente o le identità.</span><span class="sxs-lookup"><span data-stu-id="9b531-193">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="9b531-194">Quando si imposta l'ambito, è possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="9b531-194">When setting the scope, you can select:</span></span>

- <span data-ttu-id="9b531-195">Tutti i dispositivi</span><span class="sxs-lookup"><span data-stu-id="9b531-195">All devices</span></span>
- <span data-ttu-id="9b531-196">Gruppi di dispositivi specifici</span><span class="sxs-lookup"><span data-stu-id="9b531-196">Specific device groups</span></span>

<span data-ttu-id="9b531-197">Verranno interrogati solo i dati dei dispositivi nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="9b531-197">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="9b531-198">Inoltre, le azioni verranno eseguite solo su tali dispositivi.</span><span class="sxs-lookup"><span data-stu-id="9b531-198">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="9b531-199">6. Esaminare e attivare la regola.</span><span class="sxs-lookup"><span data-stu-id="9b531-199">6. Review and turn on the rule.</span></span>
<span data-ttu-id="9b531-200">Dopo aver esaminato la regola, selezionare **Crea** per salvarla.</span><span class="sxs-lookup"><span data-stu-id="9b531-200">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="9b531-201">La regola di rilevamento personalizzata viene eseguita immediatamente.</span><span class="sxs-lookup"><span data-stu-id="9b531-201">The custom detection rule immediately runs.</span></span> <span data-ttu-id="9b531-202">Viene eseguito di nuovo in base alla frequenza configurata per verificare la presenza di corrispondenze, generare avvisi ed eseguire azioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="9b531-202">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>


>[!Important] 
><span data-ttu-id="9b531-203">I rilevamenti personalizzati devono essere regolarmente esaminati per l'efficienza e l'efficacia.</span><span class="sxs-lookup"><span data-stu-id="9b531-203">Custom detections should be regularly reviewed for efficiency and effectiveness.</span></span> <span data-ttu-id="9b531-204">Per assicurarsi di creare rilevamenti che attivano avvisi veri, prendere tempo per esaminare i rilevamenti personalizzati esistenti seguendo la procedura descritta in [Gestire le regole di rilevamento personalizzate esistenti.](#manage-existing-custom-detection-rules)</span><span class="sxs-lookup"><span data-stu-id="9b531-204">To make sure you are creating detections that trigger true alerts, take time to review your existing custom detections by following the steps in [Manage existing custom detection rules](#manage-existing-custom-detection-rules).</span></span> <br>  
<span data-ttu-id="9b531-205">È possibile mantenere il controllo sull'ampia o specificità dei rilevamenti personalizzati, in modo che eventuali falsi avvisi generati da rilevamenti personalizzati potrebbero indicare la necessità di modificare determinati parametri delle regole.</span><span class="sxs-lookup"><span data-stu-id="9b531-205">You maintain control over the broadness or specificity of your custom detections so any false alerts generated by custom detections might indicate a need to modify certain parameters of the rules.</span></span>


## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="9b531-206">Gestire le regole di rilevamento personalizzate esistenti</span><span class="sxs-lookup"><span data-stu-id="9b531-206">Manage existing custom detection rules</span></span>
<span data-ttu-id="9b531-207">È possibile visualizzare l'elenco delle regole di rilevamento personalizzate esistenti, controllare le esecuzioni precedenti ed esaminare gli avvisi che hanno attivato.</span><span class="sxs-lookup"><span data-stu-id="9b531-207">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="9b531-208">È inoltre possibile eseguire una regola su richiesta e modificarla.</span><span class="sxs-lookup"><span data-stu-id="9b531-208">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="9b531-209">Visualizzare le regole esistenti</span><span class="sxs-lookup"><span data-stu-id="9b531-209">View existing rules</span></span>

<span data-ttu-id="9b531-210">Per visualizzare tutte le regole di rilevamento personalizzate esistenti, passare **a Ricerca**  >  **rilevamenti personalizzati.**</span><span class="sxs-lookup"><span data-stu-id="9b531-210">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="9b531-211">Nella pagina sono elencate tutte le regole con le seguenti informazioni di esecuzione:</span><span class="sxs-lookup"><span data-stu-id="9b531-211">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="9b531-212">**Ultima esecuzione:** data dell'ultima esecuzione di una regola per verificare la presenza di corrispondenze di query e generare avvisi</span><span class="sxs-lookup"><span data-stu-id="9b531-212">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="9b531-213">**Stato dell'ultima esecuzione:** indica se una regola è stata eseguita correttamente</span><span class="sxs-lookup"><span data-stu-id="9b531-213">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="9b531-214">**Esecuzione successiva:** l'esecuzione pianificata successiva</span><span class="sxs-lookup"><span data-stu-id="9b531-214">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="9b531-215">**Stato:** indica se una regola è stata attivata o disattivata</span><span class="sxs-lookup"><span data-stu-id="9b531-215">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="9b531-216">Visualizzare i dettagli della regola, modificare la regola ed eseguire la regola</span><span class="sxs-lookup"><span data-stu-id="9b531-216">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="9b531-217">Per visualizzare informazioni complete su una regola di rilevamento personalizzata, passare a **Ricerca** di rilevamenti  >  **personalizzati** e quindi selezionare il nome della regola.</span><span class="sxs-lookup"><span data-stu-id="9b531-217">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="9b531-218">È quindi possibile visualizzare informazioni generali sulla regola, incluse le informazioni relative allo stato di esecuzione e all'ambito.</span><span class="sxs-lookup"><span data-stu-id="9b531-218">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="9b531-219">Nella pagina è inoltre disponibile l'elenco degli avvisi e delle azioni attivati.</span><span class="sxs-lookup"><span data-stu-id="9b531-219">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="9b531-220">![Pagina dettagli regola di rilevamento personalizzata](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="9b531-220">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="9b531-221">*Dettagli delle regole di rilevamento personalizzate*</span><span class="sxs-lookup"><span data-stu-id="9b531-221">*Custom detection rule details*</span></span>

<span data-ttu-id="9b531-222">È inoltre possibile eseguire le azioni seguenti nella regola da questa pagina:</span><span class="sxs-lookup"><span data-stu-id="9b531-222">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="9b531-223">**Esegui:** eseguire immediatamente la regola.</span><span class="sxs-lookup"><span data-stu-id="9b531-223">**Run**—run the rule immediately.</span></span> <span data-ttu-id="9b531-224">In questo modo viene reimpostato anche l'intervallo per l'esecuzione successiva.</span><span class="sxs-lookup"><span data-stu-id="9b531-224">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="9b531-225">**Modifica:** modificare la regola senza modificare la query</span><span class="sxs-lookup"><span data-stu-id="9b531-225">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="9b531-226">**Modifica query**: modifica la query in ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="9b531-226">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="9b531-227">**Attivare**  /  **Disattiva:** abilita la regola o arresta l'esecuzione</span><span class="sxs-lookup"><span data-stu-id="9b531-227">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="9b531-228">**Delete:** disattivare la regola e rimuoverla</span><span class="sxs-lookup"><span data-stu-id="9b531-228">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="9b531-229">Visualizzare e gestire gli avvisi attivati</span><span class="sxs-lookup"><span data-stu-id="9b531-229">View and manage triggered alerts</span></span>

<span data-ttu-id="9b531-230">Nella schermata dei dettagli della regola (**Ricerca** di rilevamenti personalizzati  >    >  **[nome regola]**) passare a **Avvisi** attivati , in cui sono elencati gli avvisi generati dalle corrispondenze alla regola.</span><span class="sxs-lookup"><span data-stu-id="9b531-230">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="9b531-231">Selezionare un avviso per visualizzare informazioni dettagliate ed eseguire le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b531-231">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="9b531-232">Gestire l'avviso impostandone lo stato e la classificazione (avviso vero o falso)</span><span class="sxs-lookup"><span data-stu-id="9b531-232">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="9b531-233">Collegare l'avviso a un evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="9b531-233">Link the alert to an incident</span></span>
- <span data-ttu-id="9b531-234">Eseguire la query che ha attivato l'avviso per la ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="9b531-234">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="9b531-235">Rivedere le azioni</span><span class="sxs-lookup"><span data-stu-id="9b531-235">Review actions</span></span>
<span data-ttu-id="9b531-236">Nella schermata dei dettagli della regola (**Ricerca** di rilevamenti personalizzati  >    >  **[nome regola]**) passare a **Azioni** attivate , in cui sono elencate le azioni eseguite in base alle corrispondenze alla regola.</span><span class="sxs-lookup"><span data-stu-id="9b531-236">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="9b531-237">Per visualizzare rapidamente le informazioni ed eseguire azioni su un elemento di una tabella, utilizzare la colonna di selezione [&#10003;] a sinistra della tabella.</span><span class="sxs-lookup"><span data-stu-id="9b531-237">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b531-238">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b531-238">See also</span></span>
- [<span data-ttu-id="9b531-239">Panoramica dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="9b531-239">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="9b531-240">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="9b531-240">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9b531-241">Scoprire il linguaggio delle query in Ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="9b531-241">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9b531-242">Eseguire la migrazione di query di ricerca avanzate da Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="9b531-242">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
