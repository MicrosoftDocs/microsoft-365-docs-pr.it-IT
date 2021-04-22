---
title: Ricerca di minacce su dispositivi, messaggi di posta elettronica, app e identità con ricerca avanzata
description: Studiare scenari di ricerca comuni e query di esempio che riguardano dispositivi, messaggi di posta elettronica, app e identità.
keywords: ricerca avanzata, dati di Office365, dispositivi Windows, messaggi di posta elettronica di Office365 normalizzano, messaggi di posta elettronica, app, identità, ricerca delle minacce, ricerca di minacce informatiche, ricerca, query, telemetria, Microsoft 365, Microsoft 365 Defender
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
ms.openlocfilehash: 8a811d60af281bb534776736e77c3eb54ab6a760
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932966"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>Cercare minacce tra dispositivi, posta elettronica, app e identità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

[La ricerca avanzata](advanced-hunting-overview.md) in Microsoft 365 Defender consente di cercare in modo proattivo le minacce tra:
- Dispositivi gestiti da Microsoft Defender per Endpoint
- Messaggi di posta elettronica elaborati da Microsoft 365
- Attività delle app cloud, eventi di autenticazione e attività del controller di dominio monitorate da Microsoft Cloud App Security e Microsoft Defender for Identity

Con questo livello di visibilità, è possibile cercare rapidamente minacce che attraversano sezioni della rete, incluse intrusioni sofisticate che arrivano sulla posta elettronica o sul Web, elevare privilegi locali, acquisire credenziali di dominio con privilegi e passare lateralmente ai dispositivi. 

Ecco tecniche generali e query di esempio basate su diversi scenari di ricerca che consentono di esplorare come creare query durante la ricerca di minacce così sofisticate.

## <a name="get-entity-info"></a>Ottenere informazioni sull'entità
Utilizzare queste query per informazioni su come ottenere rapidamente informazioni su account utente, dispositivi e file. 

### <a name="obtain-user-accounts-from-email-addresses"></a>Ottenere account utente da indirizzi di posta elettronica
Durante la creazione di query su [tabelle che includono sia dispositivi che messaggi di posta elettronica](advanced-hunting-schema-tables.md), è probabile che sia necessario ottenere i nomi degli account utente dagli indirizzi di posta elettronica del mittente o del destinatario. In genere è possibile eseguire questa operazione per l'indirizzo del mittente o del destinatario utilizzando *l'host locale* dall'indirizzo di posta elettronica.

Nel frammento di codice seguente usiamo la funzione [tostring()](/azure/data-explorer/kusto/query/tostringfunction) Kusto per estrarre l'host locale subito prima degli indirizzi di posta elettronica dei destinatari `@` nella colonna `RecipientEmailAddress` .

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
La query seguente mostra come usare questo frammento di codice:

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a>Unire la tabella IdentityInfo

È possibile ottenere nomi di account e altre informazioni sull'account unendo o unendo la [tabella IdentityInfo.](advanced-hunting-identityinfo-table.md) La query seguente ottiene l'elenco dei rilevamenti di phishing e malware dalla tabella [EmailEvents](advanced-hunting-emailevents-table.md) e quindi unisce le informazioni alla tabella per ottenere informazioni dettagliate su `IdentityInfo` ogni destinatario. 

```kusto
EmailEvents
| where Timestamp > ago(7d)
//Get email processing events where the messages were identified as either phishing or malware
| where ThreatTypes has "Malware" or ThreatTypes has "Phish"
//Merge email events with identity info to get recipient details
| join (IdentityInfo | distinct AccountUpn, AccountDisplayName, JobTitle, 
Department, City, Country) on $left.RecipientEmailAddress == $right.AccountUpn 
//Show important message and recipient details
| project Timestamp, NetworkMessageId, Subject, ThreatTypes, 
SenderFromAddress, RecipientEmailAddress, AccountDisplayName, JobTitle, 
Department, City, Country
```

### <a name="get-device-information"></a>Ottenere informazioni sul dispositivo
Lo [schema di ricerca avanzata](advanced-hunting-schema-tables.md) fornisce informazioni dettagliate sul dispositivo in varie tabelle. Ad esempio, la [tabella DeviceInfo fornisce](advanced-hunting-deviceinfo-table.md) informazioni complete sul dispositivo in base ai dati degli eventi aggregati regolarmente. Questa query utilizza la tabella per verificare se un utente potenzialmente compromesso ( ) ha eseguito l'accesso a qualsiasi dispositivo e quindi elenca gli avvisi che sono stati attivati `DeviceInfo` `<account-name>` in tali dispositivi.

>[!Tip]
> Questa query utilizza per specificare un inner join , che impedisce `kind=inner` la deduplicazione dei valori sul lato sinistro per [](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) `DeviceId` .

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

## <a name="hunting-scenarios"></a>Scenari di ricerca

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>Elencare le attività di accesso degli utenti che hanno ricevuto messaggi di posta elettronica che non sono stati zapped correttamente
[L'eliminazione automatica di](../office-365-security/zero-hour-auto-purge.md) zero ore (ZAP) risolve i messaggi di posta elettronica dannosi dopo essere stati ricevuti. Se ZAP ha esito negativo, il codice dannoso potrebbe essere eseguito sul dispositivo e lasciare gli account compromessi. Questa query controlla l'attività di accesso effettuata dai destinatari dei messaggi di posta elettronica che non sono stati correttamente indirizzati da ZAP.

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a>Ottenere i tentativi di accesso dagli account di dominio destinati al furto di credenziali
Questa query identifica innanzitutto tutti gli avvisi di accesso alle credenziali nella `AlertInfo` tabella. Quindi unisce o unisce la tabella, analizzando i nomi degli account di destinazione e i filtri solo per gli account `AlertEvidence` aggiunti a un dominio. Infine, controlla la tabella per ottenere tutte le attività di accesso dagli account di destinazione `IdentityLogonEvents` aggiunti al dominio.

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>Verificare se nei dispositivi sono presenti file di un mittente malintenzionato noto
Presupponendo di conoscere un indirizzo di posta elettronica che invia file dannosi ( ), è possibile eseguire questa query per determinare se i file di questo mittente `MaliciousSender@example.com` esistono nei dispositivi. È possibile utilizzare questa query, ad esempio, per identificare i dispositivi interessati da una campagna di distribuzione di malware.

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>Rivedere i tentativi di accesso dopo aver ricevuto messaggi pericolosi
Questa query trova i 10 accessi più recenti eseguiti dai destinatari dei messaggi entro 30 minuti dalla ricezione di messaggi pericoloso. È possibile usare questa query per verificare se gli account dei destinatari dei messaggi di posta elettronica sono stati compromessi.

```kusto
//Define new table for malicious emails
let MaliciousEmails=EmailEvents
//List emails detected as malware, getting only pertinent columns
| where ThreatTypes has "Malware" 
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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>Esaminare le attività di PowerShell dopo la ricezione di messaggi di posta elettronica da un mittente malintenzionato noto
I messaggi di posta elettronica pericolosi contengono spesso documenti e altri allegati appositamente predisposti che eseguono comandi di PowerShell per l'esecuzione di altri payload. Se si è a conoscenza dei messaggi di posta elettronica provenienti da un mittente dannoso noto ( ), è possibile utilizzare questa query per elencare ed esaminare le attività di PowerShell che si sono verificate entro 30 minuti dopo la ricezione di un messaggio di posta elettronica dal `MaliciousSender@example.com` mittente.  

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

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Usare i risultati delle query](advanced-hunting-query-results.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Comprensione dello schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)