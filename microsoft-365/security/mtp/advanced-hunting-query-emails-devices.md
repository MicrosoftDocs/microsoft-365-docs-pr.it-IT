---
title: Trovare minacce in dispositivi e messaggi di posta elettronica con Ricerca avanzata
description: Studiare scenari di ricerca comuni e query di esempio che includano sia dispositivi che messaggi di posta elettronica.
keywords: ricerca avanzata, dati di Office365, dispositivi Windows, normalizzazione e-mail Office365, e-mail, ricerca delle minacce, ricerca delle minacce informatiche, ricerca, query, telemetria, Microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: 8310a9a57c8dc7406c0b1d56b20009b6400abcb1
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "42928985"
---
# <a name="hunt-for-threats-across-devices-and-emails"></a>Ricerca delle minacce su dispositivi ed e-mail

**Si applica a:**
- Microsoft Threat Protection



[Ricerca avanzata](advanced-hunting-overview.md) in Microsoft Threat Protection consente di cercare in modo proattivo le minacce in tutti i dispositivi Windows e nei messaggi di posta elettronica di Office 365. Di seguito sono illustrati alcuni scenari di ricerca e query di esempio che consentono di capire come creare query che includano sia dispositivi che messaggi di posta elettronica.

## <a name="obtain-user-accounts-from-email-addresses"></a>Ottenere account utente da indirizzi di posta elettronica
Durante la creazione di query su [tabelle che includono sia dispositivi che messaggi di posta elettronica](advanced-hunting-schema-tables.md), è probabile che sia necessario ottenere i nomi degli account utente dagli indirizzi di posta elettronica del mittente o del destinatario. Per farlo, usare l'*host locale* dall'indirizzo e-mail:

```kusto
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

Questa tecnica di normalizzazione viene usata negli scenari di seguito riportati.

## <a name="hunting-scenarios"></a>Scenari di ricerca

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>Verificare se nei dispositivi sono presenti file di un mittente malintenzionato noto
Se si conosce un indirizzo di posta elettronica che invia file dannosi, è possibile eseguire questa query per determinare se i file del mittente sono presenti nei dispositivi. È possibile usare questa query per determinare, ad esempio, il numero di dispositivi interessati da una campagna di distribuzione di malware.

```kusto
//Get prevalence of files sent by a malicious sender in your organization
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
| where isnotempty(SHA256)
| join (
DeviceFileEvents
| project FileName, SHA256
) on SHA256
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>Rivedere i tentativi di accesso dopo aver ricevuto messaggi pericolosi
Questa query trova i 10 accessi più recenti eseguiti dai destinatari dei messaggi entro 30 minuti dalla ricezione di messaggi pericoloso. È possibile usare questa query per verificare se gli account dei destinatari dei messaggi di posta elettronica sono stati compromessi.

```kusto
//Find logons that occurred right after malicious email was received
let MaliciousEmail=EmailEvents
| where MalwareFilterVerdict == "Malware" 
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmail
| join (
DeviceLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>Esaminare le attività di PowerShell dopo la ricezione di messaggi di posta elettronica da un mittente malintenzionato noto
I messaggi di posta elettronica pericolosi contengono spesso documenti e altri allegati appositamente predisposti che eseguono comandi di PowerShell per l'esecuzione di altri payload. Se si è a conoscenza di messaggi di posta elettronica provenienti da un mittente malintenzionato, è possibile usare questa query per elencare ed esaminare le attività di PowerShell verificatesi entro 30 minuti dalla ricezione di un messaggio di posta elettronica da parte del mittente.  

```kusto
//Find PowerShell activities right after email was received from malicious sender
let x=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
x
| join (
DeviceProcessEvents
| where FileName =~ "powershell.exe"
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Usare i risultati delle query](advanced-hunting-query-results.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Comprensione dello schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
