---
title: Creare e gestire le regole di rilevamento personalizzate in Microsoft Threat Protection
description: Informazioni su come creare e gestire le regole per i rilevamenti personalizzati in base alle query di ricerca avanzate
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, rilevamenti personalizzati, regole, schema, kusto, Microsoft 365, Microsoft Threat Protection, RBAC, autorizzazioni, Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: cdfc23f34d90c9d725ec6fb314728553a987c025
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034865"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="20b5e-104">Creare e gestire le regole per i rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="20b5e-104">Create and manage custom detections rules</span></span>

<span data-ttu-id="20b5e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="20b5e-105">**Applies to:**</span></span>
- <span data-ttu-id="20b5e-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="20b5e-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="20b5e-107">Le regole di rilevamento personalizzate create con le query di [ricerca avanzata](advanced-hunting-overview.md) consentono di monitorare in modo proattivo vari eventi e Stati del sistema, tra cui l'attività di violazione sospetta e gli endpoint non configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="20b5e-107">Custom detection rules built from [Advanced hunting](advanced-hunting-overview.md) queries let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="20b5e-108">È possibile impostare gli avvisi e le azioni di risposta ogni volta che si verificano delle corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="20b5e-108">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="20b5e-109">Autorizzazioni necessarie per la gestione dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="20b5e-109">Required permissions for managing custom detections</span></span>

<span data-ttu-id="20b5e-110">Per gestire i rilevamenti personalizzati, è necessario essere assegnati a uno di questi ruoli:</span><span class="sxs-lookup"><span data-stu-id="20b5e-110">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="20b5e-111">**Amministratore della sicurezza** : l'amministratore della sicurezza o il ruolo di amministratore della sicurezza è un [ruolo di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) per la gestione di varie impostazioni di sicurezza in Microsoft 365 Security Center e vari portali e servizi.</span><span class="sxs-lookup"><span data-stu-id="20b5e-111">**Security administrator** — the security administrator or security admin role is an [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) for managing various security settings in Microsoft 365 security center and various portals and services.</span></span>

- <span data-ttu-id="20b5e-112">**Operatore di sicurezza** : il ruolo Operatore di sicurezza è un [ruolo di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) per la gestione degli avvisi e dispone dell'accesso globale in sola lettura sulle funzionalità relative alla sicurezza, incluse tutte le informazioni disponibili in Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="20b5e-112">**Security operator** —  the security operator role is an [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) for managing alerts and has global read-only access on security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="20b5e-113">Questo ruolo è sufficiente per la gestione dei rilevamenti personalizzati solo se il controllo di accesso basato sui ruoli (RBAC) è disattivato in Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="20b5e-113">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender ATP.</span></span> <span data-ttu-id="20b5e-114">Se sono stati configurati RBAC, è necessaria anche l'autorizzazione **Gestisci impostazioni di sicurezza** per Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="20b5e-114">If you have RBAC configured, you also need the **manage security settings** permission for Microsoft Defender ATP.</span></span>

<span data-ttu-id="20b5e-115">Per gestire le autorizzazioni necessarie, un **amministratore globale** può eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20b5e-115">To manage required permissions, a **global administrator** can do the following:</span></span>

- <span data-ttu-id="20b5e-116">Assegnare l' **amministratore della sicurezza** o il ruolo di **operatore di sicurezza** nell'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com/) in **roles** > **Security admin**.</span><span class="sxs-lookup"><span data-stu-id="20b5e-116">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="20b5e-117">Controllare le impostazioni di RBAC per Microsoft Defender ATP in [Microsoft Defender Security Center](https://securitycenter.windows.com/) in **Settings** > **Permissions** > **roles**.</span><span class="sxs-lookup"><span data-stu-id="20b5e-117">Check RBAC settings for Microsoft Defender ATP in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="20b5e-118">Selezionare il ruolo corrispondente per assegnare l'autorizzazione **Gestisci impostazioni di sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="20b5e-118">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="20b5e-119">Per gestire i rilevamenti personalizzati, **gli operatori di sicurezza** avranno bisogno dell'autorizzazione **Gestisci impostazioni di sicurezza** in Microsoft Defender ATP se RBAC è attivato.</span><span class="sxs-lookup"><span data-stu-id="20b5e-119">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender ATP if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="20b5e-120">Creare una regola di rilevamento personalizzata</span><span class="sxs-lookup"><span data-stu-id="20b5e-120">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="20b5e-121">1. preparare la query.</span><span class="sxs-lookup"><span data-stu-id="20b5e-121">1. Prepare the query.</span></span>

<span data-ttu-id="20b5e-122">In Microsoft 365 Security Center, andare a **ricerca avanzata** e selezionare una query esistente o creare una nuova query.</span><span class="sxs-lookup"><span data-stu-id="20b5e-122">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="20b5e-123">Quando si utilizza una nuova query, eseguire la query per identificare gli errori e comprendere i possibili risultati.</span><span class="sxs-lookup"><span data-stu-id="20b5e-123">When using a new query, run the query to identify errors and understand possible results.</span></span>

#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="20b5e-124">Colonne obbligatorie nei risultati della query</span><span class="sxs-lookup"><span data-stu-id="20b5e-124">Required columns in the query results</span></span>
<span data-ttu-id="20b5e-125">Per creare una regola di rilevamento personalizzata, è necessario che la query restituisca le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="20b5e-125">To create a custom detection rule, the query must return the following columns:</span></span>

- `Timestamp`
- <span data-ttu-id="20b5e-126">Una delle colonne del dispositivo, dell'utente o della cassetta postale seguenti:</span><span class="sxs-lookup"><span data-stu-id="20b5e-126">One of the following device, user, or mailbox columns:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="20b5e-127">`SenderFromAddress`(mittente busta o indirizzo del percorso restituito)</span><span class="sxs-lookup"><span data-stu-id="20b5e-127">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="20b5e-128">`SenderMailFromAddress`(indirizzo mittente visualizzato dal client di posta elettronica)</span><span class="sxs-lookup"><span data-stu-id="20b5e-128">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountSid`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`
>[!NOTE]
><span data-ttu-id="20b5e-129">Il supporto per altre entità verrà aggiunto quando vengono aggiunte nuove tabelle allo [schema di caccia avanzato](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="20b5e-129">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="20b5e-130">Query semplici, ad esempio quelle che non utilizzano l' `project` operatore `summarize` or per personalizzare o aggregare i risultati, generalmente restituiscono queste colonne comuni.</span><span class="sxs-lookup"><span data-stu-id="20b5e-130">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="20b5e-131">Sono disponibili vari modi per garantire che le query più complesse restituiscano queste colonne.</span><span class="sxs-lookup"><span data-stu-id="20b5e-131">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="20b5e-132">Ad esempio, se si preferisce aggregare e contare per entità in una colonna come `DeviceId`, è comunque possibile restituire `Timestamp` ottenendolo dall'evento più recente che coinvolge ogni Unique. `DeviceId`</span><span class="sxs-lookup"><span data-stu-id="20b5e-132">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="20b5e-133">La query di esempio seguente conta il numero di computer univoci (`DeviceId`) con rilevamenti antivirus e utilizza questo conteggio per trovare solo i computer con più di cinque rilevamenti.</span><span class="sxs-lookup"><span data-stu-id="20b5e-133">The sample query below counts the number of unique machines (`DeviceId`) with antivirus detections and uses this count to find only the machines with more than five detections.</span></span> <span data-ttu-id="20b5e-134">Per restituire la versione `Timestamp`più recente, viene `summarize` utilizzato l'operatore `arg_max` con la funzione.</span><span class="sxs-lookup"><span data-stu-id="20b5e-134">To return the latest `Timestamp`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize Timestamp = max(Timestamp), count() by DeviceId
| where count_ > 5
```
### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="20b5e-135">2. creare una nuova regola e fornire informazioni dettagliate sugli avvisi.</span><span class="sxs-lookup"><span data-stu-id="20b5e-135">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="20b5e-136">Con la query nell'editor di query, selezionare **Crea regola di rilevamento** e specificare gli avvisi seguenti:</span><span class="sxs-lookup"><span data-stu-id="20b5e-136">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="20b5e-137">**Nome del rilevamento** -nome della regola di rilevamento</span><span class="sxs-lookup"><span data-stu-id="20b5e-137">**Detection name** — name of the detection rule</span></span>
- <span data-ttu-id="20b5e-138">**Frequenza** : intervallo per l'esecuzione della query e l'azione.</span><span class="sxs-lookup"><span data-stu-id="20b5e-138">**Frequency** — interval for running the query and taking action.</span></span> [<span data-ttu-id="20b5e-139">Per ulteriori informazioni, vedere</span><span class="sxs-lookup"><span data-stu-id="20b5e-139">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="20b5e-140">**Titolo avviso** -titolo visualizzato con gli avvisi attivati dalla regola</span><span class="sxs-lookup"><span data-stu-id="20b5e-140">**Alert title** — title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="20b5e-141">**Severity** -potenziale rischio del componente o dell'attività identificata dalla regola</span><span class="sxs-lookup"><span data-stu-id="20b5e-141">**Severity** — potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="20b5e-142">**Categoria** -componente di minaccia o attività identificata dalla regola</span><span class="sxs-lookup"><span data-stu-id="20b5e-142">**Category** — threat component or activity identified by the rule</span></span>
- <span data-ttu-id="20b5e-143">**Mitre att&le tecniche CK** -una o più tecniche di attacco identificate dalla regola come documentate nel [&CK Framework di Mitra](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="20b5e-143">**MITRE ATT&CK techniques** — one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/)</span></span>
- <span data-ttu-id="20b5e-144">**Descrizione** : altre informazioni sul componente o l'attività identificata dalla regola</span><span class="sxs-lookup"><span data-stu-id="20b5e-144">**Description** — more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="20b5e-145">**Azioni consigliate** : azioni aggiuntive che i risponditori potrebbero prendere in risposta a un avviso</span><span class="sxs-lookup"><span data-stu-id="20b5e-145">**Recommended actions** — additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="20b5e-146">Frequenza delle regole</span><span class="sxs-lookup"><span data-stu-id="20b5e-146">Rule frequency</span></span>
<span data-ttu-id="20b5e-147">Quando viene salvata, viene eseguita immediatamente una regola di rilevamento personalizzata nuova o modificata e vengono verificate le corrispondenze degli ultimi 30 giorni di dati.</span><span class="sxs-lookup"><span data-stu-id="20b5e-147">When saved, a new or edited custom detection rule immediately runs and checks for matches from  the past 30 days of data.</span></span> <span data-ttu-id="20b5e-148">La regola viene quindi eseguita di nuovo a intervalli fissi e le durate di lookback in base alla frequenza scelta:</span><span class="sxs-lookup"><span data-stu-id="20b5e-148">The rule then runs again at fixed intervals and lookback durations based on the frequency you choose:</span></span>

- <span data-ttu-id="20b5e-149">**Ogni 24 ore** : viene eseguito ogni 24 ore, controllando i dati degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="20b5e-149">**Every 24 hours** — runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="20b5e-150">**Ogni 12 ore** : viene eseguito ogni 12 ore, controllando i dati delle ultime 24 ore.</span><span class="sxs-lookup"><span data-stu-id="20b5e-150">**Every 12 hours** — runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="20b5e-151">**Ogni 3 ore** : viene eseguito ogni 3 ore, controllando i dati delle ultime 6 ore.</span><span class="sxs-lookup"><span data-stu-id="20b5e-151">**Every 3 hours** — runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="20b5e-152">**Ogni ora** : viene eseguito ogni ora, controllando i dati delle ultime 2 ore.</span><span class="sxs-lookup"><span data-stu-id="20b5e-152">**Every hour** — runs hourly, checking data from the past 2 hours</span></span>

<span data-ttu-id="20b5e-153">Selezionare la frequenza corrispondente alla misura in cui si desidera monitorare i rilevamenti e valutare la capacità dell'organizzazione di rispondere agli avvisi.</span><span class="sxs-lookup"><span data-stu-id="20b5e-153">Select the frequency that matches how closely you want to monitor detections, and consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="20b5e-154">3. scegliere le entità interessate.</span><span class="sxs-lookup"><span data-stu-id="20b5e-154">3. Choose the impacted entities.</span></span>
<span data-ttu-id="20b5e-155">Identificare le colonne nei risultati della query in cui si prevede di trovare l'entità interessata o con l'impatto principale.</span><span class="sxs-lookup"><span data-stu-id="20b5e-155">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="20b5e-156">Ad esempio, una query potrebbe restituire gli indirizzi`SenderFromAddress` mittente `SenderMailFromAddress`(o) e`RecipientEmailAddress`destinatario ().</span><span class="sxs-lookup"><span data-stu-id="20b5e-156">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="20b5e-157">Identificare quali di queste colonne rappresentano la principale entità interessata aiuta gli avvisi rilevanti di aggregazione del servizio, la correlazione degli incidenti e le azioni di risposta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="20b5e-157">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="20b5e-158">È possibile selezionare una sola colonna per ogni tipo di entità (cassetta postale, utente o dispositivo).</span><span class="sxs-lookup"><span data-stu-id="20b5e-158">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="20b5e-159">Le colonne non restituite dalla query non possono essere selezionate.</span><span class="sxs-lookup"><span data-stu-id="20b5e-159">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions-on-files-or-machines"></a><span data-ttu-id="20b5e-160">4. specificare le azioni su file o computer.</span><span class="sxs-lookup"><span data-stu-id="20b5e-160">4. Specify actions on files or machines.</span></span>
<span data-ttu-id="20b5e-161">La regola di rilevamento personalizzata può eseguire automaticamente azioni su file o computer restituiti dalla query.</span><span class="sxs-lookup"><span data-stu-id="20b5e-161">Your custom detection rule can automatically take actions on files or machines that are returned by the query.</span></span>

#### <a name="actions-on-machines"></a><span data-ttu-id="20b5e-162">Azioni sui computer</span><span class="sxs-lookup"><span data-stu-id="20b5e-162">Actions on machines</span></span>
<span data-ttu-id="20b5e-163">Queste azioni vengono applicate ai computer nella `DeviceId` colonna dei risultati della query:</span><span class="sxs-lookup"><span data-stu-id="20b5e-163">These actions are applied to machines in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="20b5e-164">**Isolate Machine** : utilizza Microsoft Defender ATP per applicare l'isolamento completo della rete, impedendo al computer di connettersi a qualsiasi applicazione o servizio.</span><span class="sxs-lookup"><span data-stu-id="20b5e-164">**Isolate machine** — uses Microsoft Defender ATP to apply full network isolation, preventing the machine from connecting to any application or service.</span></span> [<span data-ttu-id="20b5e-165">Altre informazioni sull'isolamento del computer ATP Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="20b5e-165">Learn more about Microsoft Defender ATP machine isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-machines-from-the-network)
- <span data-ttu-id="20b5e-166">**Raccolta del pacchetto di analisi** : raccoglie le informazioni sul computer in un file zip.</span><span class="sxs-lookup"><span data-stu-id="20b5e-166">**Collect investigation package** — collects machine information in a ZIP file.</span></span> [<span data-ttu-id="20b5e-167">Per ulteriori informazioni, vedere il pacchetto di analisi ATP Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="20b5e-167">Learn more about the Microsoft Defender ATP investigation package</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-machines)
- <span data-ttu-id="20b5e-168">**Run Antivirus Scan** : esegue un'analisi completa di Windows Defender antivirus sul computer</span><span class="sxs-lookup"><span data-stu-id="20b5e-168">**Run antivirus scan** — performs a full Windows Defender Antivirus scan on the machine</span></span>
- <span data-ttu-id="20b5e-169">**Avviare un'indagine** : avvia un' [indagine automatizzata](mtp-autoir.md) sul computer</span><span class="sxs-lookup"><span data-stu-id="20b5e-169">**Initiate investigation** — initiates an [automated investigation](mtp-autoir.md) on the machine</span></span>

#### <a name="actions-on-files"></a><span data-ttu-id="20b5e-170">Azioni sui file</span><span class="sxs-lookup"><span data-stu-id="20b5e-170">Actions on files</span></span>
<span data-ttu-id="20b5e-171">Se si seleziona questa opzione, l'azione **file di quarantena** viene eseguita `SHA1`sui `InitiatingProcessSHA1`file `SHA256`nella colonna `InitiatingProcessSHA256` ,, o dei risultati della query.</span><span class="sxs-lookup"><span data-stu-id="20b5e-171">When selected, the **Quarantine file** action is taken on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="20b5e-172">Questa azione consente di eliminare il file dal percorso corrente e di collocarne una copia in quarantena.</span><span class="sxs-lookup"><span data-stu-id="20b5e-172">This action deletes the file from its current location and places a copy in quarantine.</span></span>

> [!NOTE]
> <span data-ttu-id="20b5e-173">L'azione Consenti o blocca per le regole di rilevamento personalizzate non è attualmente supportata su Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="20b5e-173">The allow or block action for custom detection rules is currently not supported on Microsoft Threat Protection.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="20b5e-174">5. impostare l'ambito della regola.</span><span class="sxs-lookup"><span data-stu-id="20b5e-174">5. Set the rule scope.</span></span>
<span data-ttu-id="20b5e-175">Impostare l'ambito per specificare quali dispositivi sono coperti dalla regola.</span><span class="sxs-lookup"><span data-stu-id="20b5e-175">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="20b5e-176">L'ambito influenza le regole che controllano i dispositivi e non influisce sulle regole che controllano solo le cassette postali e gli account utente o le identità.</span><span class="sxs-lookup"><span data-stu-id="20b5e-176">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="20b5e-177">Quando si imposta l'ambito, è possibile selezionare:</span><span class="sxs-lookup"><span data-stu-id="20b5e-177">When setting the scope, you can select:</span></span>

- <span data-ttu-id="20b5e-178">Tutti i dispositivi</span><span class="sxs-lookup"><span data-stu-id="20b5e-178">All devices</span></span>
- <span data-ttu-id="20b5e-179">Gruppi di dispositivi specifici</span><span class="sxs-lookup"><span data-stu-id="20b5e-179">Specific device groups</span></span>

<span data-ttu-id="20b5e-180">Verrà eseguita una query solo sui dati dei dispositivi nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="20b5e-180">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="20b5e-181">Inoltre, le azioni verranno eseguite solo su tali dispositivi.</span><span class="sxs-lookup"><span data-stu-id="20b5e-181">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="20b5e-182">6. rivedere e accendere la regola.</span><span class="sxs-lookup"><span data-stu-id="20b5e-182">6. Review and turn on the rule.</span></span>
<span data-ttu-id="20b5e-183">Dopo aver esaminato la regola, fare clic su **Crea** per salvarla.</span><span class="sxs-lookup"><span data-stu-id="20b5e-183">After reviewing the rule, click **Create** to save it.</span></span> <span data-ttu-id="20b5e-184">Viene eseguita immediatamente la regola di rilevamento personalizzata.</span><span class="sxs-lookup"><span data-stu-id="20b5e-184">The custom detection rule immediately runs.</span></span> <span data-ttu-id="20b5e-185">Viene eseguito di nuovo in base alla frequenza configurata per verificare la corrispondenza, generare avvisi e prendere le azioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="20b5e-185">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="20b5e-186">Gestire le regole di rilevamento personalizzate esistenti</span><span class="sxs-lookup"><span data-stu-id="20b5e-186">Manage existing custom detection rules</span></span>
<span data-ttu-id="20b5e-187">È possibile visualizzare l'elenco delle regole di rilevamento personalizzate esistenti, verificare le relative esecuzioni precedenti ed esaminare gli avvisi che sono stati attivati.</span><span class="sxs-lookup"><span data-stu-id="20b5e-187">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="20b5e-188">È inoltre possibile eseguire una regola su richiesta e modificarla.</span><span class="sxs-lookup"><span data-stu-id="20b5e-188">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="20b5e-189">Visualizzazione delle regole esistenti</span><span class="sxs-lookup"><span data-stu-id="20b5e-189">View existing rules</span></span>

<span data-ttu-id="20b5e-190">Per visualizzare tutte le regole di rilevamento personalizzate esistenti, **passare a ricerca** > di**rilevamenti personalizzati**.</span><span class="sxs-lookup"><span data-stu-id="20b5e-190">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="20b5e-191">Nella pagina sono elencate tutte le regole con le seguenti informazioni di esecuzione:</span><span class="sxs-lookup"><span data-stu-id="20b5e-191">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="20b5e-192">**Ultima esecuzione** : quando è stata eseguita l'ultima esecuzione di una regola per verificare la corrispondenza di query e generare avvisi</span><span class="sxs-lookup"><span data-stu-id="20b5e-192">**Last run** — when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="20b5e-193">**Stato ultima esecuzione** -se una regola ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="20b5e-193">**Last run status** — whether a rule ran successfully</span></span>
- <span data-ttu-id="20b5e-194">**Esecuzione successiva** : la successiva esecuzione pianificata</span><span class="sxs-lookup"><span data-stu-id="20b5e-194">**Next run** — the next scheduled run</span></span>
- <span data-ttu-id="20b5e-195">**Stato** : se una regola è stata attivata o disattivata</span><span class="sxs-lookup"><span data-stu-id="20b5e-195">**Status** — whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="20b5e-196">Visualizzare i dettagli delle regole, modificare la regola e eseguire la regola</span><span class="sxs-lookup"><span data-stu-id="20b5e-196">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="20b5e-197">Per visualizzare informazioni complete su una regola di rilevamento personalizzata, selezionare il nome della regola nell'elenco delle regole in **caccia** > ai**rilevamenti personalizzati**.</span><span class="sxs-lookup"><span data-stu-id="20b5e-197">To view comprehensive information about a custom detection rule, select the name of rule from the list of rules in **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="20b5e-198">In questo articolo viene aperta una pagina sulla regola di rilevamento personalizzata con informazioni generali sulla regola, inclusi i dettagli dell'avviso, lo stato di esecuzione e l'ambito.</span><span class="sxs-lookup"><span data-stu-id="20b5e-198">This opens a page about the custom detection rule with general information about the rule, including the details of the alert, run status, and scope.</span></span> <span data-ttu-id="20b5e-199">Fornisce inoltre l'elenco degli avvisi attivati e delle azioni attivate.</span><span class="sxs-lookup"><span data-stu-id="20b5e-199">It also provides the list of triggered alerts and triggered actions.</span></span>

<span data-ttu-id="20b5e-200">![Pagina dei dettagli delle regole di rilevamento personalizzate](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="20b5e-200">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="20b5e-201">*Dettagli sulle regole di rilevamento personalizzate*</span><span class="sxs-lookup"><span data-stu-id="20b5e-201">*Custom detection rule details*</span></span>

<span data-ttu-id="20b5e-202">È inoltre possibile eseguire le azioni seguenti sulla regola da questa pagina:</span><span class="sxs-lookup"><span data-stu-id="20b5e-202">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="20b5e-203">**Esegui** -eseguire immediatamente la regola.</span><span class="sxs-lookup"><span data-stu-id="20b5e-203">**Run** — run the rule immediately.</span></span> <span data-ttu-id="20b5e-204">Questo reimposta anche l'intervallo per la successiva esecuzione.</span><span class="sxs-lookup"><span data-stu-id="20b5e-204">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="20b5e-205">**Modifica** : consente di modificare la regola senza modificare la query</span><span class="sxs-lookup"><span data-stu-id="20b5e-205">**Edit** — modify the rule without changing the query</span></span>
- <span data-ttu-id="20b5e-206">**Modify query** -modificare la query in Advanced Hunting</span><span class="sxs-lookup"><span data-stu-id="20b5e-206">**Modify query** — edit the query in advanced hunting</span></span>
- <span data-ttu-id="20b5e-207">**Attiva**disattivazione-Abilita la regola o Interrompi l'esecuzione**Turn off**  / </span><span class="sxs-lookup"><span data-stu-id="20b5e-207">**Turn on** / **Turn off** — enable the rule or stop it from running</span></span>
- <span data-ttu-id="20b5e-208">**Elimina (Delete** )-disattiva la regola e rimuovila</span><span class="sxs-lookup"><span data-stu-id="20b5e-208">**Delete** — turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="20b5e-209">Visualizzare e gestire gli avvisi attivati</span><span class="sxs-lookup"><span data-stu-id="20b5e-209">View and manage triggered alerts</span></span>

<span data-ttu-id="20b5e-210">Nella schermata Dettagli regola (**caccia** > **ai rilevamenti** > personalizzati **[nome regola]**), andare a **avvisi attivati** per visualizzare l'elenco degli avvisi generati dalle corrispondenze alla regola.</span><span class="sxs-lookup"><span data-stu-id="20b5e-210">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered alerts** to view the list of alerts generated by matches to the rule.</span></span> <span data-ttu-id="20b5e-211">Selezionare un avviso per visualizzare informazioni dettagliate sull'avviso e intraprendere le azioni seguenti per l'avviso:</span><span class="sxs-lookup"><span data-stu-id="20b5e-211">Select an alert to view detailed information about that alert and take the following actions on that alert:</span></span>

- <span data-ttu-id="20b5e-212">Gestire l'avviso impostando lo stato e la classificazione (avviso vero o falso)</span><span class="sxs-lookup"><span data-stu-id="20b5e-212">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="20b5e-213">Collegare l'avviso a un evento imprevisto</span><span class="sxs-lookup"><span data-stu-id="20b5e-213">Link the alert to an incident</span></span>
- <span data-ttu-id="20b5e-214">Eseguire la query che ha attivato l'avviso per la ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="20b5e-214">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="20b5e-215">Esaminare le azioni</span><span class="sxs-lookup"><span data-stu-id="20b5e-215">Review actions</span></span>
<span data-ttu-id="20b5e-216">Nella schermata Dettagli regola (**caccia** > **ai rilevamenti** > personalizzati **[nome regola]**), andare a **azioni attivate** per visualizzare l'elenco delle azioni intraprese in base alle corrispondenze alla regola.</span><span class="sxs-lookup"><span data-stu-id="20b5e-216">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions** to view the list of actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="20b5e-217">Per visualizzare rapidamente le informazioni e intervenire su un elemento di una tabella, utilizzare la colonna di selezione [&#10003;] a sinistra della tabella.</span><span class="sxs-lookup"><span data-stu-id="20b5e-217">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topic"></a><span data-ttu-id="20b5e-218">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="20b5e-218">Related topic</span></span>
- [<span data-ttu-id="20b5e-219">Panoramica dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="20b5e-219">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="20b5e-220">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="20b5e-220">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="20b5e-221">Scoprire il linguaggio delle query in Ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="20b5e-221">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
