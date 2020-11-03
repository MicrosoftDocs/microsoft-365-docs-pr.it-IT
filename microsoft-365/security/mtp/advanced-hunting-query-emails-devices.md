---
title: Cercare minacce tra dispositivi, messaggi di posta elettronica, app e identità con la ricerca avanzata
description: Studiare gli scenari di caccia comuni e le query di esempio che coprono dispositivi, messaggi di posta elettronica, app e identità.
keywords: caccia avanzata, dati di Office365, dispositivi Windows, messaggi di posta elettronica di Office365 normalizzati, posta elettronica, app, identità, caccia alle minacce, caccia alla minaccia cibernetica, ricerca, query, telemetria, Microsoft 365, Microsoft Threat Protection
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 97640c318908b87c211caed780624080508a255f
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847345"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a><span data-ttu-id="cd543-104">Cercare minacce tra dispositivi, messaggi di posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="cd543-104">Hunt for threats across devices, emails, apps, and identities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="cd543-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="cd543-105">**Applies to:**</span></span>
- <span data-ttu-id="cd543-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cd543-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="cd543-107">La [ricerca avanzata](advanced-hunting-overview.md) in Microsoft 365 Defender consente di cercare in modo proattivo le minacce che interessano:</span><span class="sxs-lookup"><span data-stu-id="cd543-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender allows you to proactively hunt for threats across:</span></span>
- <span data-ttu-id="cd543-108">Dispositivi gestiti da Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="cd543-108">Devices managed by Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="cd543-109">Messaggi di posta elettronica elaborati da Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cd543-109">Emails processed by Microsoft 365</span></span>
- <span data-ttu-id="cd543-110">Attività di app Cloud, eventi di autenticazione e attività del controller di dominio monitorate da Microsoft cloud app Security e Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="cd543-110">Cloud app activities, authentication events, and domain controller activities tracked by Microsoft Cloud App Security and Microsoft Defender for Identity</span></span>

<span data-ttu-id="cd543-111">Con questo livello di visibilità, è possibile cercare rapidamente le minacce che attraversano sezioni della rete, incluse le intrusioni sofisticate che arrivano sulla posta elettronica o sul Web, elevare i privilegi locali, acquisire le credenziali di dominio privilegiato e spostarsi lateralmente nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="cd543-111">With this level of visibility, you can quickly hunt for threats that traverse sections of your network, including sophisticated intrusions that arrive on email or the web, elevate local privileges, acquire privileged domain credentials, and move laterally to across your devices.</span></span> 

<span data-ttu-id="cd543-112">Di seguito sono riportate le tecniche generali e le query di esempio basate su diversi scenari di caccia che consentono di esplorare la modalità di creazione di query durante la ricerca di tali minacce sofisticate.</span><span class="sxs-lookup"><span data-stu-id="cd543-112">Here are general techniques and sample queries based on various hunting scenarios that can help you explore how you might construct queries when hunting for such sophisticated threats.</span></span>

## <a name="get-entity-info"></a><span data-ttu-id="cd543-113">Ottenere informazioni sulle entità</span><span class="sxs-lookup"><span data-stu-id="cd543-113">Get entity info</span></span>
<span data-ttu-id="cd543-114">Utilizzare queste query per scoprire come è possibile ottenere rapidamente informazioni sugli account utente, sui dispositivi e sui file.</span><span class="sxs-lookup"><span data-stu-id="cd543-114">Use these queries to learn how you can quickly get information about user accounts, devices, and files.</span></span> 

### <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="cd543-115">Ottenere account utente da indirizzi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="cd543-115">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="cd543-116">Durante la creazione di query su [tabelle che includono sia dispositivi che messaggi di posta elettronica](advanced-hunting-schema-tables.md), è probabile che sia necessario ottenere i nomi degli account utente dagli indirizzi di posta elettronica del mittente o del destinatario.</span><span class="sxs-lookup"><span data-stu-id="cd543-116">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="cd543-117">In genere, è possibile eseguire questa operazione per l'indirizzo del destinatario o del mittente utilizzando l' *host locale* dall'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="cd543-117">You can generally do this for either recipient or sender address using the *local-host* from the email address.</span></span>

<span data-ttu-id="cd543-118">Nel frammento di seguito viene utilizzata la funzione [ToString ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) kusto per estrarre il diritto host locale prima degli `@` indirizzi di posta elettronica del destinatario nella colonna `RecipientEmailAddress` .</span><span class="sxs-lookup"><span data-stu-id="cd543-118">In the snippet below, we use the [tostring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto function to extract the local-host right before the `@` from recipient email addresses in the column `RecipientEmailAddress`.</span></span>

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
<span data-ttu-id="cd543-119">Nella query seguente viene illustrato il modo in cui è possibile utilizzare questo frammento di pagina:</span><span class="sxs-lookup"><span data-stu-id="cd543-119">The query below shows how this snippet can be used:</span></span>

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a><span data-ttu-id="cd543-120">Unire la tabella IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="cd543-120">Merge the IdentityInfo table</span></span>

<span data-ttu-id="cd543-121">È possibile ottenere i nomi degli account e altre informazioni sull'account unendo o unendosi alla [tabella IdentityInfo](advanced-hunting-identityinfo-table.md).</span><span class="sxs-lookup"><span data-stu-id="cd543-121">You can get account names and other account information by merging or joining the [IdentityInfo table](advanced-hunting-identityinfo-table.md).</span></span> <span data-ttu-id="cd543-122">La query seguente ottiene l'elenco dei rilevamenti di phishing e malware dalla [tabella EmailEvents](advanced-hunting-emailevents-table.md) e quindi aggiunge tali informazioni alla `IdentityInfo` tabella per ottenere informazioni dettagliate su ogni destinatario.</span><span class="sxs-lookup"><span data-stu-id="cd543-122">The query below obtains the list of phishing and malware detections from the [EmailEvents table](advanced-hunting-emailevents-table.md) and then joins that information with the `IdentityInfo` table to get detailed information about each recipient.</span></span> 

```kusto
EmailEvents
| where Timestamp > ago(7d)
//Get email processing events where the messages were identified as either phishing or malware
| where MalwareFilterVerdict == 'Malware' or PhishFilterVerdict == 'Phish'
//Merge email events with identity info to get recipient details
| join (IdentityInfo | distinct AccountUpn, AccountDisplayName, JobTitle, 
Department, City, Country) on $left.RecipientEmailAddress == $right.AccountUpn 
//Show important message and recipient details
| project Timestamp, NetworkMessageId, Subject, PhishFilterVerdict, MalwareFilterVerdict,
SenderFromAddress, RecipientEmailAddress, AccountDisplayName, JobTitle, 
Department, City, Country
```

### <a name="get-device-information"></a><span data-ttu-id="cd543-123">Ottenere informazioni sul dispositivo</span><span class="sxs-lookup"><span data-stu-id="cd543-123">Get device information</span></span>
<span data-ttu-id="cd543-124">Lo [schema di ricerca avanzata](advanced-hunting-schema-tables.md) fornisce informazioni estese sul dispositivo in varie tabelle.</span><span class="sxs-lookup"><span data-stu-id="cd543-124">The [advanced hunting schema](advanced-hunting-schema-tables.md) provides extensive device information in various tables.</span></span> <span data-ttu-id="cd543-125">La [tabella DeviceInfo](advanced-hunting-deviceinfo-table.md) , ad esempio, fornisce informazioni complete sui dispositivi in base ai dati di evento aggregati regolarmente.</span><span class="sxs-lookup"><span data-stu-id="cd543-125">For example, the [DeviceInfo table](advanced-hunting-deviceinfo-table.md) provides comprehensive device information based on event data aggregated regularly.</span></span> <span data-ttu-id="cd543-126">Questa query utilizza la `DeviceInfo` tabella per controllare se un utente potenzialmente compromesso ( `<account-name>` ) ha eseguito l'accesso a tutti i dispositivi e quindi elenca gli avvisi attivati in tali dispositivi.</span><span class="sxs-lookup"><span data-stu-id="cd543-126">This query uses the `DeviceInfo` table to check if a potentially compromised user (`<account-name>`) has logged on to any devices and then lists the alerts that have been triggered on those devices.</span></span>

>[!Tip]
> <span data-ttu-id="cd543-127">Questa query utilizza `kind=inner` per specificare un [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), che impedisce la deduplicazione dei valori lato sinistro per `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="cd543-127">This query uses `kind=inner` to specify an [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), which prevents deduplication of left side values for `DeviceId`.</span></span>

```kusto
DeviceInfo
//Query for devices that the potentially compromised account has logged onto
| where LoggedOnUsers contains '<account-name>'
| distinct DeviceId
//Crosscheck devices against alert records in AlertEvidence and AlertInfo tables
| join kind=inner AlertEvidence on DeviceId
| project AlertId
//List all alerts on devices that user has logged on to
| join AlertInfo on AlertId
| project AlertId, Timestamp, Title, Severity, Category 
```

## <a name="hunting-scenarios"></a><span data-ttu-id="cd543-128">Scenari di ricerca</span><span class="sxs-lookup"><span data-stu-id="cd543-128">Hunting scenarios</span></span>

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a><span data-ttu-id="cd543-129">Elenco delle attività di accesso degli utenti che hanno ricevuto messaggi di posta elettronica che non sono stati correttamente zapped</span><span class="sxs-lookup"><span data-stu-id="cd543-129">List logon activities of users that received emails that were not zapped successfully</span></span>
<span data-ttu-id="cd543-130">[Zero-hour auto Purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) indirizza i messaggi di posta elettronica dannosi dopo che sono stati ricevuti.</span><span class="sxs-lookup"><span data-stu-id="cd543-130">[Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) addresses malicious emails after they have been received.</span></span> <span data-ttu-id="cd543-131">Se ZAP ha esito negativo, il codice dannoso potrebbe eventualmente essere eseguito nel dispositivo e lasciare gli account compromessi.</span><span class="sxs-lookup"><span data-stu-id="cd543-131">If ZAP fails, malicious code might eventually run on the device and leave accounts compromised.</span></span> <span data-ttu-id="cd543-132">Questa query consente di controllare l'attività di accesso effettuata dai destinatari dei messaggi di posta elettronica che non sono stati indirizzati correttamente da ZAP.</span><span class="sxs-lookup"><span data-stu-id="cd543-132">This query checks for logon activity made by the recipients of emails that were not successfully addressed by ZAP.</span></span>

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfully
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a><span data-ttu-id="cd543-133">Ottenere tentativi di accesso da account di dominio mirati dal furto di credenziali</span><span class="sxs-lookup"><span data-stu-id="cd543-133">Get logon attempts by domain accounts targeted by credential theft</span></span>
<span data-ttu-id="cd543-134">Questa query identifica innanzitutto tutti gli avvisi di accesso alle credenziali nella `AlertInfo` tabella.</span><span class="sxs-lookup"><span data-stu-id="cd543-134">This query first identifies all credential access alerts in the `AlertInfo` table.</span></span> <span data-ttu-id="cd543-135">Viene quindi unita o aggiunta la `AlertEvidence` tabella, che viene analizzata per i nomi degli account e dei filtri di destinazione solo per gli account aggiunti a un dominio.</span><span class="sxs-lookup"><span data-stu-id="cd543-135">It then merges or joins the `AlertEvidence` table, which it parses for the names of the targeted accounts and filters for domain-joined accounts only.</span></span> <span data-ttu-id="cd543-136">Infine, viene controllata la `IdentityLogonEvents` tabella per ottenere tutte le attività di accesso dagli account di destinazione aggiunti al dominio.</span><span class="sxs-lookup"><span data-stu-id="cd543-136">Finally, it checks the `IdentityLogonEvents` table to get all logon activities by the domain-joined targeted accounts.</span></span>

```kusto
AlertInfo
| where Timestamp > ago(30d)
//Get all credential access alerts
| where Category == "CredentialAccess"
//Get more info from AlertEvidence table to get the SID of the target accounts
| join AlertEvidence on AlertId
| extend IsJoined=(parse_json(AdditionalFields).Account.IsDomainJoined)
| extend TargetAccountSid=tostring(parse_json(AdditionalFields).Account.Sid)
//Filter for domain-joined accounts only
| where IsJoined has "true"
//Merge with IdentityLogonEvents to get all logon attempts by the potentially compromised target accounts
| join kind=inner IdentityLogonEvents on $left.TargetAccountSid == $right.AccountSid
//Show only pertinent info, such as account name, the app or service, protocol, the accessed device, and type of logon
| project AccountDisplayName, TargetAccountSid, Application, Protocol, DeviceName, LogonType
```

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="cd543-137">Verificare se nei dispositivi sono presenti file di un mittente malintenzionato noto</span><span class="sxs-lookup"><span data-stu-id="cd543-137">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="cd543-138">Presupponendo di sapere di un indirizzo di posta elettronica che invia file dannosi ( `MaliciousSender@example.com` ), è possibile eseguire questa query per determinare se i file di questo mittente sono presenti nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="cd543-138">Assuming you know of an email address sending malicious files (`MaliciousSender@example.com`), you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="cd543-139">È possibile utilizzare questa query, ad esempio per identificare i dispositivi coinvolti in una campagna di distribuzione di malware.</span><span class="sxs-lookup"><span data-stu-id="cd543-139">You can use this query, for example, to identify devices affected by a malware distribution campaign.</span></span>

```kusto
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
//Get emails with attachments identified by a SHA-256
| where isnotempty(SHA256)
| join (
//Check devices for any activity involving the attachments
DeviceFileEvents
| project FileName, SHA256
) on SHA256
| project Timestamp, FileName , SHA256, DeviceName, DeviceId,  NetworkMessageId, SenderFromAddress, RecipientEmailAddress
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="cd543-140">Rivedere i tentativi di accesso dopo aver ricevuto messaggi pericolosi</span><span class="sxs-lookup"><span data-stu-id="cd543-140">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="cd543-141">Questa query trova i 10 accessi più recenti eseguiti dai destinatari dei messaggi entro 30 minuti dalla ricezione di messaggi pericoloso.</span><span class="sxs-lookup"><span data-stu-id="cd543-141">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="cd543-142">È possibile usare questa query per verificare se gli account dei destinatari dei messaggi di posta elettronica sono stati compromessi.</span><span class="sxs-lookup"><span data-stu-id="cd543-142">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

```kusto
//Define new table for malicious emails
let MaliciousEmails=EmailEvents
//List emails detected as malware, getting only pertinent columns
| where MalwareFilterVerdict == "Malware"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmails
| join (
//Merge malicious emails with logon events to find logons by recipients
IdentityLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
//Check only logons within 30 minutes of receipt of an email
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="cd543-143">Esaminare le attività di PowerShell dopo la ricezione di messaggi di posta elettronica da un mittente malintenzionato noto</span><span class="sxs-lookup"><span data-stu-id="cd543-143">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="cd543-144">I messaggi di posta elettronica pericolosi contengono spesso documenti e altri allegati appositamente predisposti che eseguono comandi di PowerShell per l'esecuzione di altri payload.</span><span class="sxs-lookup"><span data-stu-id="cd543-144">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="cd543-145">Se si è a conoscenza di messaggi di posta elettronica provenienti da un mittente noto `MaliciousSender@example.com` , è possibile utilizzare questa query per elencare ed esaminare le attività di PowerShell che si sono verificate entro 30 minuti dopo la ricezione di un messaggio di posta elettronica da parte del mittente.</span><span class="sxs-lookup"><span data-stu-id="cd543-145">If you are aware of emails coming from a known malicious sender (`MaliciousSender@example.com`), you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender.</span></span>  

```kusto
//Define new table for emails from specific sender
let EmailsFromBadSender=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
//Merge emails from sender with process-related events on devices
EmailsFromBadSender
| join (
DeviceProcessEvents
//Look for PowerShell activity
| where FileName =~ "powershell.exe"
//Add line below to check only events initiated by Outlook
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
//Check only PowerShell activities within 30 minutes of receipt of an email
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a><span data-ttu-id="cd543-146">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="cd543-146">Related topics</span></span>
- [<span data-ttu-id="cd543-147">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="cd543-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cd543-148">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="cd543-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="cd543-149">Usare i risultati delle query</span><span class="sxs-lookup"><span data-stu-id="cd543-149">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="cd543-150">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="cd543-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="cd543-151">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="cd543-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="cd543-152">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="cd543-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
