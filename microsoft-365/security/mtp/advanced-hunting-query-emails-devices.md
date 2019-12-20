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
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: da985621c1cee3fe5aa30d961380ef3f3d83de8d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808751"
---
# <a name="hunt-for-threats-across-devices-and-emails"></a><span data-ttu-id="c2155-104">Ricerca delle minacce su dispositivi ed e-mail</span><span class="sxs-lookup"><span data-stu-id="c2155-104">Hunt for threats across devices and emails</span></span>

<span data-ttu-id="c2155-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c2155-105">**Applies to:**</span></span>
- <span data-ttu-id="c2155-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c2155-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="c2155-107">[Ricerca avanzata](advanced-hunting-overview.md) in Microsoft Threat Protection consente di cercare in modo proattivo le minacce in tutti i dispositivi Windows e nei messaggi di posta elettronica di Office 365.</span><span class="sxs-lookup"><span data-stu-id="c2155-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft Threat Protection allows you to proactively hunt for threats across your Windows devices and Office 365 emails.</span></span> <span data-ttu-id="c2155-108">Di seguito sono illustrati alcuni scenari di ricerca e query di esempio che consentono di capire come creare query che includano sia dispositivi che messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c2155-108">Here are some hunting scenarios and sample queries that can help you explore how you might construct queries covering both devices and emails.</span></span>

## <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="c2155-109">Ottenere account utente da indirizzi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="c2155-109">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="c2155-110">Durante la creazione di query su [tabelle che includono sia dispositivi che messaggi di posta elettronica](advanced-hunting-schema-tables.md), è probabile che sia necessario ottenere i nomi degli account utente dagli indirizzi di posta elettronica del mittente o del destinatario.</span><span class="sxs-lookup"><span data-stu-id="c2155-110">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="c2155-111">Per farlo, usare l'*host locale* dall'indirizzo e-mail:</span><span class="sxs-lookup"><span data-stu-id="c2155-111">To do this use the *local-host* from the email address:</span></span>

```
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

<span data-ttu-id="c2155-112">Questa tecnica di normalizzazione viene usata negli scenari di seguito riportati.</span><span class="sxs-lookup"><span data-stu-id="c2155-112">This normalization technique is used in the succeeding scenarios.</span></span>

## <a name="hunting-scenarios"></a><span data-ttu-id="c2155-113">Scenari di ricerca</span><span class="sxs-lookup"><span data-stu-id="c2155-113">Hunting scenarios</span></span>

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="c2155-114">Verificare se nei dispositivi sono presenti file di un mittente malintenzionato noto</span><span class="sxs-lookup"><span data-stu-id="c2155-114">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="c2155-115">Se si conosce un indirizzo di posta elettronica che invia file dannosi, è possibile eseguire questa query per determinare se i file del mittente sono presenti nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c2155-115">Assuming you know of an email address sending malicious files, you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="c2155-116">È possibile usare questa query per determinare, ad esempio, il numero di dispositivi interessati da una campagna di distribuzione di malware.</span><span class="sxs-lookup"><span data-stu-id="c2155-116">You can use this query, for example, to determine the number of devices affected by a malware distribution campaign.</span></span>

```
//Get prevalence of files sent by a malicious sender in your organization
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
| where isnotempty(SHA256)
| join (
DeviceFileEvents
| project FileName, SHA256
) on SHA256
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="c2155-117">Rivedere i tentativi di accesso dopo aver ricevuto messaggi pericolosi</span><span class="sxs-lookup"><span data-stu-id="c2155-117">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="c2155-118">Questa query trova i 10 accessi più recenti eseguiti dai destinatari dei messaggi entro 30 minuti dalla ricezione di messaggi pericoloso.</span><span class="sxs-lookup"><span data-stu-id="c2155-118">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="c2155-119">È possibile usare questa query per verificare se gli account dei destinatari dei messaggi di posta elettronica sono stati compromessi.</span><span class="sxs-lookup"><span data-stu-id="c2155-119">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

```
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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="c2155-120">Esaminare le attività di PowerShell dopo la ricezione di messaggi di posta elettronica da un mittente malintenzionato noto</span><span class="sxs-lookup"><span data-stu-id="c2155-120">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="c2155-121">I messaggi di posta elettronica pericolosi contengono spesso documenti e altri allegati appositamente predisposti che eseguono comandi di PowerShell per l'esecuzione di altri payload.</span><span class="sxs-lookup"><span data-stu-id="c2155-121">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="c2155-122">Se si è a conoscenza di messaggi di posta elettronica provenienti da un mittente malintenzionato, è possibile usare questa query per elencare ed esaminare le attività di PowerShell verificatesi entro 30 minuti dalla ricezione di un messaggio di posta elettronica da parte del mittente.</span><span class="sxs-lookup"><span data-stu-id="c2155-122">If you are aware of emails coming from a known malicious sender, you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender .</span></span>  

```
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

## <a name="related-topics"></a><span data-ttu-id="c2155-123">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c2155-123">Related topics</span></span>
- [<span data-ttu-id="c2155-124">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="c2155-124">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c2155-125">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="c2155-125">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c2155-126">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="c2155-126">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c2155-127">Comprensione dello schema</span><span class="sxs-lookup"><span data-stu-id="c2155-127">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c2155-128">Applicazione delle procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="c2155-128">Apply query best practices</span></span>](advanced-hunting-best-practices.md)