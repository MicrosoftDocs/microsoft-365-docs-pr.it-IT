---
title: Creare e gestire regole di rilevamento personalizzate in Microsoft 365 Defender
description: Informazioni su come creare e gestire regole di rilevamento personalizzate basate su query di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, microsoft threat protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, rilevamenti personalizzati, regole, schema, kusto, Microsoft 365, Microsoft Threat Protection, RBAC, autorizzazioni, Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d58292f658446259bfab5b1b55c8b462d081421c
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080624"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="4c6f3-104">Creare e gestire regole di rilevamento personalizzate</span><span class="sxs-lookup"><span data-stu-id="4c6f3-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4c6f3-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="4c6f3-105">**Applies to:**</span></span>
- <span data-ttu-id="4c6f3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4c6f3-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4c6f3-107">Le regole di rilevamento personalizzate sono regole che è possibile progettare e modificare utilizzando [query di ricerca](advanced-hunting-overview.md) avanzata.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-107">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="4c6f3-108">Queste regole consentono di monitorare in modo proattivo diversi eventi e stati di sistema, tra cui attività di violazione sospetta e endpoint non configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-108">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="4c6f3-109">Puoi impostarli per l'esecuzione a intervalli regolari, generando avvisi ed eseguire azioni di risposta ogni volta che sono presenti corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-109">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="4c6f3-110">Autorizzazioni necessarie per la gestione dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="4c6f3-110">Required permissions for managing custom detections</span></span>

<span data-ttu-id="4c6f3-111">Per gestire i rilevamenti personalizzati, è necessario disporre di uno di questi ruoli:</span><span class="sxs-lookup"><span data-stu-id="4c6f3-111">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="4c6f3-112">**Amministratore della** sicurezza: gli utenti con questo [ruolo di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) possono gestire le impostazioni di sicurezza nel Centro sicurezza Microsoft 365 e in altri portali e servizi.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-112">**Security administrator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="4c6f3-113">**Operatore della** sicurezza: gli utenti con questo ruolo di [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) possono gestire gli avvisi e avere accesso globale in sola lettura alle funzionalità correlate alla sicurezza, incluse tutte le informazioni nel Centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-113">**Security operator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="4c6f3-114">Questo ruolo è sufficiente per gestire i rilevamenti personalizzati solo se il controllo dell'accesso basato sui ruoli (RBAC) è disattivato in Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-114">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="4c6f3-115">Se RBAC è configurato, è necessaria anche l'autorizzazione per gestire le impostazioni **di** sicurezza per Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-115">If you have RBAC configured, you also need the **manage security settings** permission for Defender for Endpoint.</span></span>

<span data-ttu-id="4c6f3-116">Per gestire le autorizzazioni necessarie, un **amministratore globale** può:</span><span class="sxs-lookup"><span data-stu-id="4c6f3-116">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="4c6f3-117">Assegnare **il ruolo di amministratore della** sicurezza o **operatore** di sicurezza nell'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com/) in Amministratore **sicurezza**  >  **ruoli.**</span><span class="sxs-lookup"><span data-stu-id="4c6f3-117">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="4c6f3-118">Controllare le impostazioni RBAC per Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) in **Ruoli**  >  **autorizzazioni**  >  **impostazioni.**</span><span class="sxs-lookup"><span data-stu-id="4c6f3-118">Check RBAC settings for Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="4c6f3-119">Selezionare il ruolo corrispondente per assegnare **l'autorizzazione per la gestione delle impostazioni di** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-119">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="4c6f3-120">Per gestire i rilevamenti personalizzati,  gli **operatori** della sicurezza dovranno disporre dell'autorizzazione per gestire le impostazioni di sicurezza in Microsoft Defender per Endpoint se RBAC è attivato.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-120">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender for Endpoint if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="4c6f3-121">Creare una regola di rilevamento personalizzata</span><span class="sxs-lookup"><span data-stu-id="4c6f3-121">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="4c6f3-122">1. Preparare la query.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-122">1. Prepare the query.</span></span>

<span data-ttu-id="4c6f3-123">Nel Centro sicurezza Microsoft 365 passare a **Ricerca avanzata** e selezionare una query esistente o creare una nuova query.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-123">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="4c6f3-124">Quando si utilizza una nuova query, eseguire la query per identificare gli errori e comprendere i possibili risultati.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-124">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="4c6f3-125">Per impedire al servizio di restituire troppi avvisi, ogni regola può generare solo 100 avvisi ogni volta che viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-125">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="4c6f3-126">Prima di creare una regola, modificare la query per evitare avvisi per le normali attività quotidiane.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-126">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="4c6f3-127">Colonne obbligatorie nei risultati della query</span><span class="sxs-lookup"><span data-stu-id="4c6f3-127">Required columns in the query results</span></span>
<span data-ttu-id="4c6f3-128">Per creare una regola di rilevamento personalizzata, la query deve restituire le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c6f3-128">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="4c6f3-129">`Timestamp`: usato per impostare il timestamp per gli avvisi generati</span><span class="sxs-lookup"><span data-stu-id="4c6f3-129">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="4c6f3-130">`ReportId`: abilita le ricerche per i record originali</span><span class="sxs-lookup"><span data-stu-id="4c6f3-130">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="4c6f3-131">Una delle colonne seguenti che identificano dispositivi, utenti o cassette postali specifici:</span><span class="sxs-lookup"><span data-stu-id="4c6f3-131">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="4c6f3-132">`SenderFromAddress` (mittente della busta o Return-Path destinatario)</span><span class="sxs-lookup"><span data-stu-id="4c6f3-132">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="4c6f3-133">`SenderMailFromAddress` (indirizzo del mittente visualizzato dal client di posta elettronica)</span><span class="sxs-lookup"><span data-stu-id="4c6f3-133">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="4c6f3-134">Il supporto per entità aggiuntive verrà aggiunto man quando vengono aggiunte nuove tabelle allo [schema di ricerca avanzata.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="4c6f3-134">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="4c6f3-135">Query semplici, ad esempio quelle che non utilizzano l'operatore or per personalizzare o aggregare i risultati, in genere restituiscono `project` `summarize` queste colonne comuni.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-135">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="4c6f3-136">Esistono diversi modi per garantire che query più complesse restituiranno queste colonne.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-136">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="4c6f3-137">Ad esempio, se si preferisce aggregare e contare per entità in una colonna come , è comunque possibile restituire e ottenere dall'evento più recente che coinvolge `DeviceId` `Timestamp` ogni elemento `ReportId` `DeviceId` univoco.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-137">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="4c6f3-138">La query di esempio seguente conta il numero di dispositivi univoci ( ) con rilevamenti antivirus e usa questo conteggio per trovare solo i dispositivi con più di `DeviceId` cinque rilevamenti.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-138">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="4c6f3-139">Per restituire l'ultima `Timestamp` e la `ReportId` corrispondente, viene utilizzato `summarize` l'operatore con la `arg_max` funzione.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-139">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="4c6f3-140">Per migliorare le prestazioni delle query, impostare un filtro temporale che corrisponda alla frequenza di esecuzione prevista per la regola.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-140">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="4c6f3-141">Poiché l'esecuzione meno frequente _è ogni 24 ore,_ il filtro per il giorno precedente copre tutti i nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-141">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="4c6f3-142">2. Creare una nuova regola e fornire i dettagli dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-142">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="4c6f3-143">Con la query nell'editor di query, selezionare Crea regola **di** rilevamento e specificare i dettagli dell'avviso seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c6f3-143">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="4c6f3-144">**Nome rilevamento**- Nome della regola di rilevamento</span><span class="sxs-lookup"><span data-stu-id="4c6f3-144">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="4c6f3-145">**Frequenza:** intervallo per l'esecuzione della query e l'esecuzione di un'azione.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-145">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="4c6f3-146">Vedi altre indicazioni di seguito</span><span class="sxs-lookup"><span data-stu-id="4c6f3-146">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="4c6f3-147">**Titolo dell'avviso**: titolo visualizzato con gli avvisi attivati dalla regola</span><span class="sxs-lookup"><span data-stu-id="4c6f3-147">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="4c6f3-148">**Gravità :** potenziale rischio del componente o dell'attività identificata dalla regola</span><span class="sxs-lookup"><span data-stu-id="4c6f3-148">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="4c6f3-149">**Categoria:** componente della minaccia o attività identificata dalla regola</span><span class="sxs-lookup"><span data-stu-id="4c6f3-149">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="4c6f3-150">**MiTRE ATT&CK:** una o più tecniche di attacco identificate dalla regola come documentato nel [framework MITRE ATT&CK.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="4c6f3-150">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="4c6f3-151">Questa sezione è nascosta per alcune categorie di avviso, tra cui malware, ransomware, attività sospette e software indesiderato</span><span class="sxs-lookup"><span data-stu-id="4c6f3-151">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="4c6f3-152">**Descrizione:** ulteriori informazioni sul componente o sull'attività identificata dalla regola</span><span class="sxs-lookup"><span data-stu-id="4c6f3-152">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="4c6f3-153">**Azioni consigliate:** azioni aggiuntive che i risponditori potrebbero intraprendere in risposta a un avviso</span><span class="sxs-lookup"><span data-stu-id="4c6f3-153">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="4c6f3-154">Frequenza delle regole</span><span class="sxs-lookup"><span data-stu-id="4c6f3-154">Rule frequency</span></span>
<span data-ttu-id="4c6f3-155">Quando si salva o si modifica una nuova regola, viene eseguita e viene verificata la presenza di corrispondenze degli ultimi 30 giorni di dati.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-155">When you save or edit a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="4c6f3-156">La regola viene quindi rieseguiti a intervalli fissi, applicando una durata di lookback in base alla frequenza scelta:</span><span class="sxs-lookup"><span data-stu-id="4c6f3-156">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="4c6f3-157">**Ogni 24 ore:** viene eseguito ogni 24 ore, controllando i dati degli ultimi 30 giorni</span><span class="sxs-lookup"><span data-stu-id="4c6f3-157">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="4c6f3-158">**Ogni 12 ore:** viene eseguito ogni 12 ore, controllando i dati delle ultime 24 ore</span><span class="sxs-lookup"><span data-stu-id="4c6f3-158">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="4c6f3-159">**Ogni 3 ore:** viene eseguito ogni 3 ore, controllando i dati delle ultime 6 ore</span><span class="sxs-lookup"><span data-stu-id="4c6f3-159">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="4c6f3-160">**Ogni ora:** viene eseguita ogni ora, controllando i dati delle ultime 2 ore</span><span class="sxs-lookup"><span data-stu-id="4c6f3-160">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

>[!TIP]
> <span data-ttu-id="4c6f3-161">Associare i filtri tempo nella query alla durata di lookback.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-161">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="4c6f3-162">I risultati al di fuori della durata del lookback vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-162">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="4c6f3-163">Selezionare la frequenza che corrisponde alla frequenza con cui si desidera monitorare i rilevamenti.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-163">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="4c6f3-164">Considerare la capacità dell'organizzazione di rispondere agli avvisi.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-164">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="4c6f3-165">3. Scegliere le entità influenzate.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-165">3. Choose the impacted entities.</span></span>
<span data-ttu-id="4c6f3-166">Identificare le colonne nei risultati della query in cui si prevede di trovare l'entità principale interessata o interessata.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-166">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="4c6f3-167">Ad esempio, una query potrebbe restituire gli indirizzi del mittente ( `SenderFromAddress` o ) e del `SenderMailFromAddress` destinatario ( `RecipientEmailAddress` ).</span><span class="sxs-lookup"><span data-stu-id="4c6f3-167">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="4c6f3-168">L'identificazione di quale di queste colonne rappresenta l'entità impacted principale consente al servizio di aggregare avvisi pertinenti, correlare gli eventi imprevisti e le azioni di risposta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-168">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="4c6f3-169">È possibile selezionare una sola colonna per ogni tipo di entità (cassetta postale, utente o dispositivo).</span><span class="sxs-lookup"><span data-stu-id="4c6f3-169">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="4c6f3-170">Le colonne non restituite dalla query non possono essere selezionate.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-170">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="4c6f3-171">4. Specificare le azioni.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-171">4. Specify actions.</span></span>
<span data-ttu-id="4c6f3-172">La regola di rilevamento personalizzata può eseguire automaticamente azioni su dispositivi, file o utenti restituiti dalla query.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-172">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="4c6f3-173">Azioni nei dispositivi</span><span class="sxs-lookup"><span data-stu-id="4c6f3-173">Actions on devices</span></span>
<span data-ttu-id="4c6f3-174">Queste azioni vengono applicate ai dispositivi nella `DeviceId` colonna dei risultati della query:</span><span class="sxs-lookup"><span data-stu-id="4c6f3-174">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="4c6f3-175">**Isola dispositivo:** usa Microsoft Defender per Endpoint per applicare l'isolamento di rete completo, impedendo al dispositivo di connettersi a qualsiasi applicazione o servizio.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-175">**Isolate device**—uses Microsoft Defender for Endpoint to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="4c6f3-176">Altre informazioni sull'isolamento del computer di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4c6f3-176">Learn more about Microsoft Defender for Endpoint machine isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="4c6f3-177">**Raccogliere il pacchetto di** analisi: raccoglie le informazioni sul dispositivo in un file ZIP.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-177">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="4c6f3-178">Altre informazioni sul pacchetto di analisi di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4c6f3-178">Learn more about the Microsoft Defender for Endpoint investigation package</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="4c6f3-179">**Eseguire l'analisi antivirus:** esegue un'Windows Defender antivirus completa nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="4c6f3-179">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="4c6f3-180">**Avviare un'indagine:** avvia [un'indagine](mtp-autoir.md) automatizzata nel dispositivo</span><span class="sxs-lookup"><span data-stu-id="4c6f3-180">**Initiate investigation**—initiates an [automated investigation](mtp-autoir.md) on the device</span></span>
- <span data-ttu-id="4c6f3-181">**Limita l'esecuzione dell'app:** imposta restrizioni sul dispositivo per consentire l'esecuzione solo dei file firmati con un certificato emesso da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-181">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="4c6f3-182">Altre informazioni sulle restrizioni per le app con Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4c6f3-182">Learn more about app restrictions with Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="4c6f3-183">Azioni sui file</span><span class="sxs-lookup"><span data-stu-id="4c6f3-183">Actions on files</span></span>
<span data-ttu-id="4c6f3-184">Se questa opzione è selezionata, è possibile scegliere di applicare l'azione Del **file** in quarantena ai file nella colonna , , o dei `SHA1` risultati della `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` query.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-184">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="4c6f3-185">Questa azione elimina il file dalla posizione corrente e ne mette in quarantena una copia.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-185">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="4c6f3-186">Azioni sugli utenti</span><span class="sxs-lookup"><span data-stu-id="4c6f3-186">Actions on users</span></span>
<span data-ttu-id="4c6f3-187">Se selezionata, **l'azione** Contrassegna utente come compromessa viene eseguita sugli utenti nella `AccountObjectId` colonna , o nella colonna dei risultati della `InitiatingProcessAccountObjectId` `RecipientObjectId` query.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-187">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="4c6f3-188">Questa azione imposta il livello di rischio degli utenti su "alto" in Azure Active Directory, attivando i criteri [di protezione delle identità corrispondenti.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)</span><span class="sxs-lookup"><span data-stu-id="4c6f3-188">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="4c6f3-189">L'azione consenti o blocca per le regole di rilevamento personalizzate non è attualmente supportata in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-189">The allow or block action for custom detection rules is currently not supported on Microsoft 365 Defender.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="4c6f3-190">5. Impostare l'ambito della regola.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-190">5. Set the rule scope.</span></span>
<span data-ttu-id="4c6f3-191">Impostare l'ambito per specificare quali dispositivi sono coperti dalla regola.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-191">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="4c6f3-192">L'ambito influenza le regole che controllano i dispositivi e non influisce sulle regole che controllano solo le cassette postali e gli account utente o le identità.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-192">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="4c6f3-193">Quando si imposta l'ambito, è possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="4c6f3-193">When setting the scope, you can select:</span></span>

- <span data-ttu-id="4c6f3-194">Tutti i dispositivi</span><span class="sxs-lookup"><span data-stu-id="4c6f3-194">All devices</span></span>
- <span data-ttu-id="4c6f3-195">Gruppi di dispositivi specifici</span><span class="sxs-lookup"><span data-stu-id="4c6f3-195">Specific device groups</span></span>

<span data-ttu-id="4c6f3-196">Verranno interrogati solo i dati dei dispositivi nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-196">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="4c6f3-197">Inoltre, le azioni verranno eseguite solo su tali dispositivi.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-197">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="4c6f3-198">6. Rivedere e attivare la regola.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-198">6. Review and turn on the rule.</span></span>
<span data-ttu-id="4c6f3-199">Dopo aver esaminato la regola, selezionare **Crea** per salvarla.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-199">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="4c6f3-200">La regola di rilevamento personalizzata viene eseguita immediatamente.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-200">The custom detection rule immediately runs.</span></span> <span data-ttu-id="4c6f3-201">Viene eseguito di nuovo in base alla frequenza configurata per verificare la presenza di corrispondenze, generare avvisi ed eseguire azioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-201">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="4c6f3-202">Gestire le regole di rilevamento personalizzate esistenti</span><span class="sxs-lookup"><span data-stu-id="4c6f3-202">Manage existing custom detection rules</span></span>
<span data-ttu-id="4c6f3-203">Puoi visualizzare l'elenco delle regole di rilevamento personalizzate esistenti, controllarne le esecuzioni precedenti ed esaminare gli avvisi che hanno attivato.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-203">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="4c6f3-204">È inoltre possibile eseguire una regola su richiesta e modificarla.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-204">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="4c6f3-205">Visualizzare le regole esistenti</span><span class="sxs-lookup"><span data-stu-id="4c6f3-205">View existing rules</span></span>

<span data-ttu-id="4c6f3-206">Per visualizzare tutte le regole di rilevamento personalizzate esistenti, passare **a Ricerca**  >  **rilevamenti personalizzati.**</span><span class="sxs-lookup"><span data-stu-id="4c6f3-206">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="4c6f3-207">Nella pagina sono elencate tutte le regole con le seguenti informazioni di esecuzione:</span><span class="sxs-lookup"><span data-stu-id="4c6f3-207">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="4c6f3-208">**Ultima esecuzione:** data dell'ultima esecuzione di una regola per verificare la presenza di corrispondenze alle query e generare avvisi</span><span class="sxs-lookup"><span data-stu-id="4c6f3-208">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="4c6f3-209">**Stato dell'ultima esecuzione:** indica se una regola è stata eseguita correttamente</span><span class="sxs-lookup"><span data-stu-id="4c6f3-209">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="4c6f3-210">**Esecuzione successiva:** l'esecuzione pianificata successiva</span><span class="sxs-lookup"><span data-stu-id="4c6f3-210">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="4c6f3-211">**Stato**: indica se una regola è stata attivata o disattivata</span><span class="sxs-lookup"><span data-stu-id="4c6f3-211">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="4c6f3-212">Visualizzare i dettagli della regola, modificare la regola ed eseguire la regola</span><span class="sxs-lookup"><span data-stu-id="4c6f3-212">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="4c6f3-213">Per visualizzare informazioni complete su una regola di rilevamento personalizzata, passare a **Ricerca** rilevamenti personalizzati e quindi  >   selezionare il nome della regola.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-213">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="4c6f3-214">È quindi possibile visualizzare informazioni generali sulla regola, incluse le informazioni relative allo stato di esecuzione e all'ambito.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-214">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="4c6f3-215">La pagina fornisce anche l'elenco di avvisi e azioni attivati.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-215">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="4c6f3-216">![Pagina dei dettagli della regola di rilevamento personalizzata](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="4c6f3-216">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="4c6f3-217">*Dettagli delle regole di rilevamento personalizzate*</span><span class="sxs-lookup"><span data-stu-id="4c6f3-217">*Custom detection rule details*</span></span>

<span data-ttu-id="4c6f3-218">È inoltre possibile eseguire le azioni seguenti nella regola da questa pagina:</span><span class="sxs-lookup"><span data-stu-id="4c6f3-218">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="4c6f3-219">**Esegui:** esegui la regola immediatamente.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-219">**Run**—run the rule immediately.</span></span> <span data-ttu-id="4c6f3-220">In questo modo viene reimpostato anche l'intervallo per l'esecuzione successiva.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-220">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="4c6f3-221">**Modifica:** modificare la regola senza modificare la query</span><span class="sxs-lookup"><span data-stu-id="4c6f3-221">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="4c6f3-222">**Modifica query**: modifica la query nella ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="4c6f3-222">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="4c6f3-223">**Attivare**  /  **Disattivare:** abilitare o arrestare l'esecuzione della regola</span><span class="sxs-lookup"><span data-stu-id="4c6f3-223">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="4c6f3-224">**Elimina:** disattivare la regola e rimuoverla</span><span class="sxs-lookup"><span data-stu-id="4c6f3-224">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="4c6f3-225">Visualizzare e gestire gli avvisi attivati</span><span class="sxs-lookup"><span data-stu-id="4c6f3-225">View and manage triggered alerts</span></span>

<span data-ttu-id="4c6f3-226">Nella schermata dei dettagli della regola (**Ricerca** rilevamenti personalizzati  >    >  **[nome regola]**) passare a **Avvisi** attivati, in cui sono elencati gli avvisi generati dalle corrispondenze alla regola.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-226">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="4c6f3-227">Selezionare un avviso per visualizzare informazioni dettagliate ed eseguire le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c6f3-227">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="4c6f3-228">Gestire l'avviso impostandone lo stato e la classificazione (avviso vero o falso)</span><span class="sxs-lookup"><span data-stu-id="4c6f3-228">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="4c6f3-229">Collegare l'avviso a un evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="4c6f3-229">Link the alert to an incident</span></span>
- <span data-ttu-id="4c6f3-230">Eseguire la query che ha attivato l'avviso per la ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="4c6f3-230">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="4c6f3-231">Rivedere le azioni</span><span class="sxs-lookup"><span data-stu-id="4c6f3-231">Review actions</span></span>
<span data-ttu-id="4c6f3-232">Nella schermata dei dettagli della regola (**Ricerca** rilevamenti personalizzati [nome della regola] ), passare a Azioni attivate , in cui sono elencate le azioni eseguite in base alle  >    >  corrispondenze alla regola. </span><span class="sxs-lookup"><span data-stu-id="4c6f3-232">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="4c6f3-233">Per visualizzare rapidamente le informazioni ed eseguire un'azione su un elemento di una tabella, utilizzare la colonna di selezione [&#10003;] a sinistra della tabella.</span><span class="sxs-lookup"><span data-stu-id="4c6f3-233">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c6f3-234">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c6f3-234">See also</span></span>
- [<span data-ttu-id="4c6f3-235">Panoramica dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="4c6f3-235">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="4c6f3-236">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="4c6f3-236">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4c6f3-237">Scoprire il linguaggio delle query in Ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="4c6f3-237">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4c6f3-238">Eseguire la migrazione di query di ricerca avanzata da Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="4c6f3-238">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mdatp.md)
