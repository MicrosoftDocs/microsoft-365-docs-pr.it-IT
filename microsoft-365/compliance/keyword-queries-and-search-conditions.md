---
title: Query delle parole chiave e condizioni di ricerca per ricerca contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.SearchQueryLearnMore
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: c4639c2e-7223-4302-8e0d-b6e10f1c3be3
ms.custom:
- seo-marvel-apr2020
description: Informazioni sui messaggi di posta elettronica e sulle proprietà dei file che è possibile cercare nel centro conformità & sicurezza di Office 365.
ms.openlocfilehash: 90365889ed60a5250514fa50b8034d5cfcb904bd
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127181"
---
# <a name="keyword-queries-and-search-conditions-for-content-search"></a>Query con parole chiave e condizioni di ricerca per Ricerca contenuto

In questo argomento vengono descritte le proprietà di posta elettronica e di documento che è possibile cercare negli elementi di posta elettronica in Exchange Online e i documenti archiviati nei siti di SharePoint e OneDrive for business utilizzando la funzionalità di ricerca contenuto nel centro sicurezza & conformità. È inoltre possibile utilizzare i cmdlet ** \* -ComplianceSearch** in PowerShell per la sicurezza & Compliance Center per cercare queste proprietà. Nell'argomento sono inoltre descritti i seguenti argomenti:   
  
- Utilizzo di operatori di ricerca booleani, condizioni di ricerca e altre tecniche di query di ricerca per affinare i risultati della ricerca.
    
- Ricerca di tipi di dati riservati e tipi di dati sensibili personalizzati in SharePoint e OneDrive for business.
    
- Ricerca di contenuto del sito condiviso con utenti esterni all'organizzazione
    
Per istruzioni dettagliate su come creare una ricerca di contenuto, vedere [Content search in Office 365](content-search.md).

  
> [!NOTE]
> Ricerca di contenuto nel centro sicurezza & compliance e nei cmdlet di ** \* ComplianceSearch** corrispondenti nel centro sicurezza & conformità PowerShell utilizzare la parola chiave Query Language (KQL). Per informazioni più dettagliate, vedere [Keyword Query Language Reference Syntax](https://go.microsoft.com/fwlink/?LinkId=269603). 
  
## <a name="searchable-email-properties"></a>Proprietà di posta elettronica disponibili per la ricerca

Nella tabella seguente sono elencate le proprietà dei messaggi di posta elettronica che possono essere cercate utilizzando la funzionalità Ricerca contenuto nel centro sicurezza & Compliance oppure utilizzando il cmdlet **New-ComplianceSearch** o **set-ComplianceSearch** . Nella tabella è incluso un esempio della sintassi _Property: value_ per ogni proprietà e una descrizione dei risultati della ricerca restituiti dagli esempi. È possibile digitare queste `property:value` coppie nella casella parole chiave per una ricerca di contenuto. 

> [!NOTE]
> Durante la ricerca delle proprietà di posta elettronica, non è possibile cercare gli elementi in cui la proprietà specificata è vuota o vuoto. Ad esempio, se si utilizza la coppia *Property: value* dell' **oggetto: ""** per cercare i messaggi di posta elettronica con una riga dell'oggetto vuota, verranno restituiti zero risultati. Questo vale anche per la ricerca delle proprietà del sito e del contatto.
  
|**Proprietà**|**Descrizione proprietà**|**Esempi**|**Risultati di ricerca restituiti dagli esempi**|
|:-----|:-----|:-----|:-----|
|AttachmentNames|I nomi dei file allegati a un messaggio di posta elettronica.|`attachmentnames:annualreport.ppt`  <br/> `attachmentnames:annual*` <br/> attachmentnames:.pptx|Messaggi che contengono un file allegato denominato annualreport.ppt. Nel secondo esempio, utilizzando il carattere jolly si ottengono dei messaggi contenenti la parola "annual" nel nome file di un allegato. Nel terzo esempio vengono restituiti tutti gli allegati con estensione di file PPTX.|
|Ccn|Il campo Ccn di un messaggio di posta elettronica. <sup>1</sup>|`bcc:pilarp@contoso.com`  <br/> `bcc:pilarp`  <br/> `bcc:"Pilar Pinilla"`|Tutti gli esempi restituiscono messaggi contenenti Pilar Pinilla nel campo Bcc (Ccn).|
|Category| Le categorie da cercare. Le categorie possono essere definite dagli utenti tramite Outlook o Outlook sul Web (in precedenza noto come Outlook Web App). I valori possibili sono i seguenti:  <br/><br/>  blu  <br/>  verde  <br/>  arancione  <br/>  viola  <br/>  rosso  <br/>  giallo|`category:"Red Category"`|I messaggi ai quali è stata assegnata la categoria di colore rosso nelle cassette postali di origine. |
|CC|Campo CC di un messaggio di posta elettronica. <sup>1</sup>|`cc:pilarp@contoso.com`  <br/> `cc:"Pilar Pinilla"`|In entrambi gli esempi, i messaggi con Pilar Pinilla specificati nel campo CC.|
|FolderId|ID della cartella (GUID) di una cartella della cassetta postale specifica. Se si utilizza questa proprietà, assicurarsi di eseguire una ricerca nella cassetta postale in cui si trova la cartella specificata. Verrà eseguita la ricerca solo nella cartella specificata. Tutte le sottocartelle della cartella non verranno cercate. Per eseguire la ricerca nelle sottocartelle, è necessario utilizzare la proprietà FolderId per la sottocartella che si desidera ricercare.  <br/> Per ulteriori informazioni sulla ricerca della proprietà folderid e sull'utilizzo di uno script per ottenere gli ID della cartella per una cassetta postale specifica, vedere [use content search for Targeted Collections](use-content-search-for-targeted-collections.md).|`folderid:4D6DD7F943C29041A65787E30F02AD1F00000000013A0000`  <br/> `folderid:2370FB455F82FC44BE31397F47B632A70000000001160000 AND participants:garthf@contoso.com`|Nel primo esempio vengono restituiti tutti gli elementi nella cartella della cassetta postale specificata. Nel secondo esempio vengono restituiti tutti gli elementi della cartella delle cassette postali specificata inviati o ricevuti da garthf@contoso.com.|
|From|Il mittente di un messaggio di posta elettronica. <sup>1</sup>|`from:pilarp@contoso.com`  <br/> `from:contoso.com`|I messaggi inviati dall'utente specificato o da un dominio specificato.|
|HasAttachment|Indica se un messaggio ha un allegato. Utilizzare i valori **true** o **false**.|`from:pilar@contoso.com AND hasattachment:true`|Messaggi inviati dall'utente specificato con allegati.|
|Importanza|The importance of an email message, which a sender can specify when sending a message. By default, messages are sent with normal importance, unless the sender sets the importance as **high** or **low**.|`importance:high`  <br/> `importance:medium`  <br/> `importance:low`|I messaggi contrassegnati con priorità alta, media o bassa.|
|IsRead|Indica se i messaggi sono stati letti. Utilizzare i valori **true** o **false**.|`isread:true`  <br/> `isread:false`|Nel primo esempio vengono restituiti i messaggi con la proprietà leggere impostata su **true**. Nel secondo esempio vengono restituiti i messaggi con la proprietà leggere impostata su **false**.|
|ItemClass|Utilizzare questa proprietà per eseguire la ricerca di tipi di dati di terze parti specifici che l'organizzazione ha importato in Office 365. Per questa proprietà, utilizzare la sintassi seguente:`itemclass:ipm.externaldata.<third-party data type>*`|`itemclass:ipm.externaldata.Facebook* AND subject:contoso`  <br/> `itemclass:ipm.externaldata.Twitter* AND from:"Ann Beebe" AND "Northwind Traders"`|Nel primo esempio vengono restituiti gli elementi di Facebook che contengono la parola "contoso" nella proprietà Subject. Nel secondo esempio vengono restituiti gli elementi di Twitter inviati da Ann Beebe e che contengono la frase parola chiave "Northwind Traders".  <br/> Per un elenco completo dei valori da utilizzare per i tipi di dati di terze parti per la proprietà ItemClass, vedere [utilizzare la ricerca contenuto per cercare i dati di terze parti che sono stati importati in Office 365](use-content-search-to-search-third-party-data-that-was-imported.md).|
|Tipo| Il tipo di messaggio di posta elettronica da cercare. Valori possibili:  <br/>  contatti  <br/>  documenti  <br/>  email  <br/>  externaldata  <br/>  fax  <br/>  im  <br/>  riviste  <br/>  riunioni  <br/>  microsoftteams (restituisce elementi da chat, riunioni e chiamate in Microsoft Teams)  <br/>  Note  <br/>  messaggi  <br/>  rssfeeds  <br/>  attività  <br/>  Voicemail|`kind:email`  <br/> `kind:email OR kind:im OR kind:voicemail`  <br/> `kind:externaldata`|Nel primo esempio vengono restituiti messaggi di posta elettronica che soddisfano i criteri di ricerca. Nel secondo esempio vengono restituiti i messaggi di posta elettronica, le conversazioni di messaggistica istantanea (incluse le conversazioni di Skype for business e le chat in Microsoft Teams) e i messaggi vocali che soddisfano i criteri di ricerca. Nel terzo esempio vengono restituiti gli elementi che sono stati importati nelle cassette postali in Microsoft 365 da origini dati di terze parti, ad esempio Twitter, Facebook e Cisco Jabber, che soddisfano i criteri di ricerca. Per ulteriori informazioni, vedere [archiviazione dei dati di terze parti in Office 365](https://www.microsoft.com/?ref=go).|
|Partecipanti|Tutti i campi persone in un messaggio di posta elettronica. Questi campi sono da, a, CC e Ccn.<sup>1</sup>|`participants:garthf@contoso.com`  <br/> `participants:contoso.com`|Messages sent by or sent to garthf@contoso.com. The second example returns all messages sent by or sent to a user in the contoso.com domain.|
|Ricevuto|La data in cui un messaggio di posta elettronica viene ricevuto da un destinatario.|`received:04/15/2016`  <br/> `received>=01/01/2016 AND received<=03/31/2016`|Messaggi ricevuti il 15 aprile 2016. Nel secondo esempio vengono restituiti tutti i messaggi ricevuti tra il 1 ° gennaio 2016 e il 31 marzo 2016.|
|Destinatari|Tutti i campi dei destinatari in un messaggio di posta elettronica. Questi campi sono a, CC e Ccn.<sup>1</sup>|`recipients:garthf@contoso.com`  <br/> `recipients:contoso.com`|Messages sent to garthf@contoso.com. The second example returns messages sent to any recipient in the contoso.com domain.|
|Inviati|La data in cui un messaggio di posta elettronica viene inviato dal mittente.|`sent:07/01/2016`  <br/> `sent>=06/01/2016 AND sent<=07/01/2016`|I messaggi inviati in una data specifica o entro l'intervallo di date specificato.|
|Dimensioni|Le dimensioni di un elemento, in byte.|`size>26214400`  <br/> `size:1..1048567`|Messaggi di dimensioni superiori a 25? MB. Il secondo esempio restituisce i messaggi di dimensioni comprese tra 1 e 1.048.567 byte (1 MB).|
|Oggetto|Il testo nella riga dell'oggetto di un messaggio di posta elettronica.  <br/> **Nota:** Quando si utilizza la proprietà Subject in una query, la ricerca restituisce tutti i messaggi in cui la riga dell'oggetto contiene il testo che si sta cercando. In altre parole, la query non restituisce solo i messaggi che hanno una corrispondenza esatta. Ad esempio, se si cerca `subject:"Quarterly Financials"` , i risultati includono i messaggi con l'oggetto "Financials trimestrali 2018".|`subject:"Quarterly Financials"`  <br/> `subject:northwind`|Messaggi che contengono la frase "Financials trimestrali" in qualsiasi punto del testo della riga dell'oggetto. Il secondo esempio restituisce tutti i messaggi che contengono la parola northwind nella riga dell'oggetto.|
|A|Campo a di un messaggio di posta elettronica. <sup>1</sup>|`to:annb@contoso.com`  <br/> `to:annb ` <br/> `to:"Ann Beebe"`|Tutti gli esempi restituiscono i messaggi in cui è specificato l'utente Ann Beebe nella riga To: (A:).|
|||||
   
> [!NOTE]
> <sup>1</sup> per il valore di una proprietà del destinatario, è possibile utilizzare l'indirizzo di posta elettronica (denominato anche *nome dell'entità utente* o UPN), il nome visualizzato o l'alias per specificare un utente. Ad esempio, è possibile usare annb@contoso.com, annb o "Ann Beebe" per specificare l'utente Ann Beebe.<br/><br/>Quando si esegue una ricerca in una delle proprietà del destinatario (da, a, CC, Ccn, partecipanti e destinatari), Microsoft 365 tenta di espandere l'identità di ogni utente cercandoli in Azure Active Directory.  Se l'utente viene trovato in Azure Active Directory, la query viene espansa per includere l'indirizzo di posta elettronica (o UPN) dell'utente, l'alias, il nome visualizzato e l'attributo LegacyExchangeDN.<br/><br/>Ad esempio, una query come `participants:ronnie@contoso.com` si espande a `participants:ronnie@contoso.com OR participants:ronnie OR participants:"Ronald Nelson" OR participants:"<LegacyExchangeDN>"` .<br/><br/>Per impedire l'espansione dei destinatari, è possibile aggiungere un asterisco (Wild Card character) alla fine dell'indirizzo di posta elettronica nella query di ricerca. ad esempio, `participants:ronnie@contoso.com*` .

## <a name="searchable-site-properties"></a>Proprietà dei siti disponibili per la ricerca

Nella tabella seguente sono riportate alcune delle proprietà di SharePoint e OneDrive for business che è possibile cercare utilizzando la funzionalità Ricerca contenuto nel centro sicurezza & Compliance oppure utilizzando il cmdlet **New-ComplianceSearch** o **set-ComplianceSearch** . Nella tabella è incluso un esempio della sintassi _Property: value_ per ogni proprietà e una descrizione dei risultati della ricerca restituiti dagli esempi. 
  
Per un elenco completo delle proprietà di SharePoint di cui è possibile eseguire la ricerca, vedere [Overview of indicizzazione e managed properties in SharePoint](https://go.microsoft.com/fwlink/p/?LinkId=331599). È possibile cercare le proprietà contrassegnate con un **Sì** nella colonna **Queryable** . 
  
|**Proprietà**|**Descrizione proprietà**|**Esempio**|**Risultati di ricerca restituiti dagli esempi**|
|:-----|:-----|:-----|:-----|
|Author|Il campo dell'autore dei documenti di Office, che persiste se un documento viene copiato. Ad esempio, se un utente crea un documento e lo invia tramite posta elettronica a qualcun altro che lo carica in SharePoint, il documento conserva comunque l'autore originale. Assicurarsi di utilizzare il nome visualizzato dell'utente per questa proprietà.|`author:"Garth Fort"`|Tutti i documenti creati da Garth Fort.|
|ContentType|Tipo di contenuto di SharePoint di un elemento, ad esempio un elemento, un documento o un video.|`contenttype:document`|Vengono restituiti tutti i documenti.|
|Creato|La data di creazione di un elemento.|`created>=06/01/2016`|Tutti gli elementi creati in o dopo il 1 ° giugno 2016.|
|CreatedBy|L'utente che ha creato o caricato un elemento. Assicurarsi di utilizzare il nome visualizzato dell'utente per questa proprietà.|`createdby:"Garth Fort"`|Tutti gli elementi creati o caricati da Garth Fort.|
|DetectedLanguage|La lingua di un elemento.|`detectedlanguage:english`|Tutti gli elementi in lingua inglese.|
|DocumentLink|Il percorso (URL) di una cartella specifica in un sito di SharePoint o OneDrive for business. Se si utilizza questa proprietà, assicurarsi di eseguire una ricerca nel sito in cui si trova la cartella specificata.  <br/> Per restituire gli elementi che si trovano in sottocartelle della cartella specificata per la proprietà documentlink, è necessario aggiungere/ \* all'URL della cartella specifica, ad esempio`documentlink: "https://contoso.sharepoint.com/Shared Documents/*"`  <br/> <br/>Per ulteriori informazioni sulla ricerca della proprietà documentlink e sull'utilizzo di uno script per ottenere gli URL di documentlink per le cartelle di un sito specifico, vedere [use content search for Targeted Collections](use-content-search-for-targeted-collections.md).|`documentlink:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Private"`  <br/> `documentlink:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Shared with Everyone/*" AND filename:confidential`|Nel primo esempio vengono restituiti tutti gli elementi della cartella OneDrive for business specificata. Nel secondo esempio vengono restituiti i documenti nella cartella del sito specificata (e in tutte le sottocartelle) che contengono la parola "confidenziale" nel nome del file.|
|FileExtension|L'estensione di un file; ad esempio, docx, 1, pptx o xlsx.|`fileextension:xlsx`|Tutti i file di Excel (Excel 2007 e versioni successive)|
|FileName|Il nome di un file.|`filename:"marketing plan"`  <br/> `filename:estimate`|The first example returns files with the exact phrase "marketing plan" in the title. The second example returns files with the word "estimate" in the file name.|
|LastModifiedTime|La data dell'ultima modifica di un elemento.|`lastmodifiedtime>=05/01/2016`  <br/> `lastmodifiedtime>=05/10/2016 AND lastmodifiedtime<=06/1/2016`|Nel primo esempio vengono restituiti gli elementi che sono stati modificati in o dopo il 1 ° maggio 2016. Nel secondo esempio vengono restituiti gli elementi modificati tra il 1 ° maggio 2016 e il 1 ° giugno 2016.|
|ModifiedBy|L'autore dell'ultima modifica di un elemento. Assicurarsi di utilizzare il nome visualizzato dell'utente per questa proprietà.|`modifiedby:"Garth Fort"`|Tutti gli elementi in cui l’ultima modifica è stata apportata da Garth Fort.|
|Percorso|Percorso (URL) di un sito specifico in un sito di SharePoint o OneDrive for business.  <br/> Per restituire gli elementi che si trovano nelle cartelle del sito specificati per la proprietà Path, è necessario aggiungere/ \* all'URL del sito specificato, ad esempio`path: "https://contoso.sharepoint.com/Shared Documents/*"`  <br/> <br/> **Nota:** L'utilizzo della `Path` proprietà per la ricerca nei percorsi di OneDrive non restituirà file multimediali, ad esempio file con estensione png, TIFF o WAV, nei risultati della ricerca. Utilizzare una proprietà diversa del sito nella query di ricerca per cercare i file multimediali nelle cartelle di OneDrive. <br/>|`path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/"`  <br/> `path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/*" AND filename:confidential`|Nel primo esempio vengono restituiti tutti gli elementi del sito di OneDrive for business specificato. Nel secondo esempio vengono restituiti i documenti nel sito e nelle cartelle specificati nel sito che contengono la parola "confidenziale" nel nome del file.|
|SharedWithUsersOWSUser|Documenti che sono stati condivisi con l'utente specificato e visualizzati nella pagina **condivisi con me** nel sito di OneDrive for business dell'utente. Si tratta di documenti che sono stati condivisi in modo esplicito con l'utente specificato da altre persone dell'organizzazione. Quando si esportano documenti che corrispondono a una query di ricerca in cui viene utilizzata la proprietà SharedWithUsersOWSUser, i documenti vengono esportati dal percorso del contenuto originale della persona che ha condiviso il documento con l'utente specificato. Per ulteriori informazioni, vedere [ricerca di contenuto del sito condiviso all'interno dell'organizzazione](#searching-for-site-content-shared-within-your-organization).|`sharedwithusersowsuser:garthf`  <br/> `sharedwithusersowsuser:"garthf@contoso.com"`|Entrambi gli esempi restituiscono tutti i documenti interni che sono stati condivisi in modo esplicito con Garth Fort e che vengono visualizzati nella pagina **condiviso con me** nell'account OneDrive for business di Garth Fort.|
|Sito|L'URL di un sito o di un gruppo di siti nell'organizzazione.|`site:"https://contoso-my.sharepoint.com"`  <br/> `site:"https://contoso.sharepoint.com/sites/teams"`|Nel primo esempio vengono restituiti gli elementi dei siti di OneDrive for business per tutti gli utenti dell'organizzazione. Il secondo esempio restituisce gli elementi di tutti i siti dei team.|
|Dimensioni|Le dimensioni di un elemento, in byte.|`size>=1`  <br/> `size:1..10000`|The first example returns items larger than 1 byte. The second example returns items from 1 through 10,000 bytes in size.|
|Titolo|Il titolo del documento. La proprietà title è metadati specificata nei documenti di Microsoft Office. È diverso dal nome del file del documento.|`title:"communication plan"`|Qualsiasi documento contenente la frase "communication plan" nella proprietà di metadati Title di un documento di Office.|
|||||
   
## <a name="searchable-contact-properties"></a>Proprietà contatto disponibili per la ricerca

Nella tabella seguente sono elencate le proprietà dei contatti indicizzate e che è possibile cercare utilizzando la ricerca contenuto. Di seguito sono riportate le proprietà disponibili per gli utenti da configurare per i contatti (denominati anche contatti personali) che si trovano nella Rubrica personale della cassetta postale di un utente. Per cercare i contatti, è possibile selezionare le cassette postali da cercare e quindi utilizzare una o più proprietà dei contatti nella query di parole chiave.
  
> [!TIP]
> Per cercare valori che contengono spazi o caratteri speciali, utilizzare virgolette doppie ("") per contenere la frase. ad esempio, `businessaddress:"123 Main Street"` . 
  
|**Proprietà**|**Descrizione proprietà**|
|:-----|:-----|
|BusinessAddress|L'indirizzo nella proprietà dell' **indirizzo aziendale** . La proprietà viene chiamata anche indirizzo di **lavoro** nella pagina delle proprietà dei contatti.|
|BusinessPhone|Il numero di telefono in una delle proprietà del numero di **telefono dell'azienda** .|
|CompanyName|Nome della proprietà **Company** .|
|Reparto|Nome della proprietà **Department** .|
|DisplayName|Il nome visualizzato del contatto. Questo è il nome della proprietà **nome completo** del contatto.|
|EmailAddress|L'indirizzo di qualsiasi proprietà dell'indirizzo di posta elettronica per il contatto. Gli utenti possono aggiungere più indirizzi di posta elettronica per un contatto. L'utilizzo di questa proprietà restituirà i contatti che corrispondono a qualsiasi indirizzo di posta elettronica del contatto.|
|FileAs|Il **file come** proprietà. Questa proprietà viene utilizzata per specificare il modo in cui il contatto è elencato nell'elenco contatti dell'utente. Ad esempio, un contatto può essere elencato come *FirstName, LastName* o *LastName, FirstName*.|
|GivenName|Nome della proprietà **First Name** .|
|HomeAddress|L'indirizzo in una delle proprietà dell'indirizzo di **casa** .|
|HomePhone|Il numero di telefono in una delle proprietà del numero di telefono di **casa** .|
|IMAddress|La proprietà dell'indirizzo di messaggistica istantanea, che in genere è un indirizzo di posta elettronica utilizzato per la messaggistica immediata.|
|MiddleName|Nome nella proprietà **Middle** Name.|
|MobilePhone|Il numero di telefono nella proprietà del numero di telefono **cellulare** .|
|Nickname|Nome della proprietà **Nickname** .|
|OfficeLocation|Valore della proprietà location di **Office** o **Office** .|
|OtherAddress|Valore per l' **altra** proprietà Address.|
|Cognome|Nome nella proprietà **Last** Name.|
|Titolo|Il titolo nella proprietà del **titolo del processo** .|
|||||

## <a name="searchable-sensitive-data-types"></a>Tipi di dati sensibili disponibili per la ricerca

È possibile utilizzare la funzionalità Ricerca contenuto nel centro sicurezza e conformità per cercare dati riservati, ad esempio numeri di carta di credito o numeri di previdenza sociale, archiviati nei documenti di SharePoint e di siti di OneDrive for business. È possibile eseguire questa operazione utilizzando la `SensitiveType` proprietà e il nome di un tipo di informazioni riservate in una query di parole chiave. Ad esempio, la query `SensitiveType:"Credit Card Number"` restituisce i documenti che contengono un numero di carta di credito. La query `SensitiveType:"U.S. Social Security Number (SSN)"` restituisce i documenti che contengono un numero di previdenza sociale degli Stati Uniti. Per visualizzare un elenco dei tipi di dati riservati che è possibile cercare, passare a **classificazioni** \> **tipi di informazioni riservate** nel centro sicurezza & conformità. In alternativa, è possibile utilizzare il cmdlet **Get-DlpSensitiveInformationType** in PowerShell per la sicurezza & Compliance Center per visualizzare un elenco di tipi di informazioni riservate. 
  
È inoltre possibile utilizzare la `SensitiveType` proprietà per cercare il nome di un tipo di informazioni riservate personalizzato creato dall'utente (o da un altro amministratore) per l'organizzazione. È possibile utilizzare la colonna **Publisher** nella pagina **tipi di informazioni riservate** nel centro sicurezza & Compliance (o la proprietà **Publisher** in PowerShell) per differenziare i tipi di informazioni riservate incorporate e personalizzate. Per ulteriori informazioni, vedere [creare un tipo di informazioni riservate personalizzato](create-a-custom-sensitive-information-type.md).
  
Per ulteriori informazioni sulla creazione di query tramite la `SensitiveType` proprietà, vedere [form a query to find sensitive data stored in sites](form-a-query-to-find-sensitive-data-stored-on-sites.md).

> [!NOTE]
> Non è possibile utilizzare i tipi di dati riservati e la `SensitiveType` Proprietà Search per cercare i dati riservati in-Rest nelle cassette postali di Exchange Online. Tuttavia, è possibile utilizzare i criteri di prevenzione della perdita di dati (DLP) per proteggere i dati sensibili del messaggio di posta elettronica in transito. Per ulteriori informazioni, vedere [Panoramica dei criteri di prevenzione della perdita di dati](data-loss-prevention-policies.md) e [cercare e trovare i dati personali](search-for-and-find-personal-data.md).
  
## <a name="search-operators"></a>Operatori di ricerca

Gli operatori di ricerca booleani, come **and**, **or**e **not**, consentono di definire ricerche più precise includendo o escludendo parole specifiche nella query di ricerca. Altre tecniche, ad esempio l'utilizzo di operatori di proprietà, ad esempio \> = o..., tra virgolette, parentesi e caratteri jolly, consentono di affinare una query di ricerca. Nella tabella seguente vengono elencati gli operatori che è possibile utilizzare per circoscrivere o ampliare i risultati della ricerca. 
  
|**Operatore**|**Usage**|**Descrizione**|
|:-----|:-----|:-----|
|E|keyword1 AND keyword2|Restituisce gli elementi che includono tutte le parole chiave o le `property:value` espressioni specificate. Ad esempio, `from:"Ann Beebe" AND subject:northwind` restituisce tutti i messaggi inviati da Ann Beebe che contengono la parola Northwind nella riga dell'oggetto. <sup>2</sup>|
|+|keyword1 + keyword2 + keyword3|Restituisce gli elementi che *contengono* `keyword2` o `keyword3` *e* che contengono anche `keyword1` .   Questo esempio è pertanto equivalente alla query `(keyword2 OR keyword3) AND keyword1` .  <br/> La query `keyword1 + keyword2` (con uno spazio dopo il **+** simbolo) non è uguale all'utilizzo dell'operatore **and** . Questa query equivale a `"keyword1 + keyword2"` restituire gli elementi con la fase esatta `"keyword1 + keyword2"` .|
|OPPURE|keyword1 OR keyword2|Restituisce gli elementi che includono una o più parole chiave o `property:value` espressioni specificate. <sup>2</sup>|
|NON|keyword1 NOT keyword2  <br/> NOT from:"Ann Beebe"  <br/> NOT Kind: im|Esclude gli elementi specificati da una parola chiave o da un' `property:value` espressione. Nel secondo esempio vengono esclusi i messaggi inviati da Ann Beebe. Nel terzo esempio vengono escluse le conversazioni di messaggistica istantanea, ad esempio le conversazioni di Skype for business salvate nella cartella della cassetta postale cronologia conversazioni. <sup>2</sup>|
|-|keyword1-keyword2|Equivale all'operatore **NOT**. In questo modo, la query restituisce elementi che contengono `keyword1` e escludono gli elementi che contengono `keyword2` .|
|VICINO|keyword1 NEAR(n) keyword2|Restituisce gli elementi con parole che sono una accanto all'altra, dove n equivale al numero delle parole separate. Ad esempio, `best NEAR(5) worst` restituisce tutti gli elementi in cui la parola "Worst" è all'interno di cinque parole "Best". Se non viene specificato alcun numero, la distanza predefinita è di otto parole. <sup>2</sup>|
|:|Proprietà: valore|I due punti (:) nella `property:value` sintassi specifica che il valore della proprietà che si sta cercando contiene il valore specificato. Ad esempio, `recipients:garthf@contoso.com` restituisce tutti i messaggi inviati a garthf@contoso.com.|
|=|Proprietà = valore|Lo stesso dell'operatore **:** .|
|\<|valore della proprietà \<|Indica che la proprietà da cercare è inferiore al valore specificato.  <sup>1</sup>|
|\>|valore della proprietà \>|Indica che la proprietà da cercare è superiore al valore specificato. <sup>1</sup>|
|\<=|proprietà \< = valore|Indica che la proprietà da cercare è minore o uguale a un valore specifico. <sup>1</sup>|
|\>=|proprietà \> = valore|Indica che la proprietà da cercare è maggiore o uguale a un valore specifico. <sup>1</sup>|
|..|Proprietà: value1.. valore2|Indica che la proprietà da cercare è maggiore o uguale a value1 e minore o uguale a value2. <sup>1</sup>|
|"  "|"fair value"  <br/> subject:"Quarterly Financials"|Utilizzare le virgolette doppie ("") per cercare una frase esatta o un termine nelle query di ricerca e parole chiave `property:value` .|
|\*|gatto\*  <br/> oggetto: set\*|Le ricerche con caratteri jolly prefix (in cui l'asterisco è posizionato alla fine di una parola) corrispondono a zero o a più caratteri nelle parole chiave o nelle `property:value` query. Ad esempio, `title:set*` restituisce i documenti che contengono il set di parole, il programma di installazione e l'impostazione (e altre parole che iniziano con "set") nel titolo del documento.  <br/><br/> **Nota:** È possibile utilizzare solo le ricerche con caratteri jolly prefix. ad esempio, **Cat \* ** o **set \* **. Le ricerche suffisso (** \* Cat** ), le ricerche infissi (**c \* t**) e le ricerche di sottostringhe (** \* Cat \* **) non sono supportate.|
|(  )| (fair OR free) AND (from:contoso.com)  <br/>  (IPO OR initial) AND (stock OR shares)  <br/>  (quarterly financials)|Parentesi raggruppare le frasi booleane, `property:value` gli elementi e le parole chiave. Ad esempio, `(quarterly financials)` restituisce gli elementi che contengono le parole Quarterly e Financials.|
|||||
   
> [!NOTE]
> <sup>1</sup> utilizzare questo operatore per le proprietà che dispongono di valori numerici o di data.<br/> <sup>2</sup> gli operatori di ricerca booleani devono essere in caratteri maiuscoli. ad esempio, **e**. Se si utilizza un operatore in caratteri minuscoli **, ad esempio, verrà**considerato come una parola chiave nella query di ricerca. 
  
## <a name="search-conditions"></a>Condizioni di ricerca

È possibile aggiungere condizioni a una query di ricerca per restringere una ricerca e restituire un insieme di risultati più raffinato. Ogni condizione aggiunge una clausola alla query di ricerca KQL creata ed eseguita all'avvio della ricerca.
  
[Condizioni per le proprietà comuni ](#conditions-for-common-properties)

[Condizioni per le proprietà della posta](#conditions-for-mail-properties)

[Condizioni per le proprietà dei documenti](#conditions-for-document-properties)

[Operatori utilizzati con condizioni](#operators-used-with-conditions)

[Linee guida per l'uso di condizioni](#guidelines-for-using-conditions)

[Esempi](#examples-of-using-conditions-in-search-queries)
  
### <a name="conditions-for-common-properties"></a>Condizioni per le proprietà comuni

Creare una condizione utilizzando le proprietà comuni quando si cercano cassette postali e siti nella stessa ricerca. Nella tabella seguente sono elencate le proprietà disponibili da utilizzare per l'aggiunta di una condizione.
  
|**Condizione**|**Descrizione**|
|:-----|:-----|
|Data|Per la posta elettronica, la data di un messaggio ricevuto da un destinatario o inviato da un mittente. Per i documenti, la data dell'Ultima modifica di un documento.|
|Mittente/autore|Per la posta elettronica, l'utente che ha inviato un messaggio. Per i documenti, l'utente menzionato nel campo dell'autore dei documenti di Office. È possibile digitare più nomi, separati da virgole. Due o più valori sono collegati logicamente dall'operatore **OR**.|
|Dimensione (in byte)|Per la posta elettronica e i documenti, la dimensione dell'elemento (in byte).|
|Subject/title|Per la posta elettronica, il testo nella riga dell'oggetto di un messaggio. Per i documenti, il titolo del documento. Come spiegato in precedenza, la proprietà title è costituita da metadati specificati nei documenti di Microsoft Office. È possibile digitare il nome di più di un oggetto/titolo, separati da virgole. Due o più valori sono collegati logicamente dall'operatore **OR**.|
|Etichetta di conformità|Per la posta elettronica e i documenti, le etichette di conservazione che sono state assegnate automaticamente ai messaggi e ai documenti dai criteri di etichettatura automatica o dalle etichette di conservazione che sono state assegnate manualmente dagli utenti. Le etichette di conservazione vengono utilizzate per classificare la posta elettronica e i documenti per la governance delle informazioni e applicare le regole di conservazione in base alle impostazioni definite dall'etichetta. È possibile digitare parte del nome dell'etichetta di conservazione e utilizzare un carattere jolly oppure digitare il nome dell'etichetta completo. Per ulteriori informazioni sulle etichette di conservazione, vedere informazioni [sui criteri di conservazione e sulle etichette di conservazione](retention.md).|
|||
  
### <a name="conditions-for-mail-properties"></a>Condizioni per le proprietà della posta

Creare una condizione utilizzando le proprietà della posta quando si effettuano ricerche in cassette postali o cartelle pubbliche. Nella tabella seguente vengono elencate le proprietà della posta elettronica che è possibile utilizzare per una condizione. Queste proprietà sono un sottoinsieme delle proprietà di posta elettronica descritte in precedenza. Queste descrizioni vengono ripetute per la vostra convenienza.
  
|**Condizione**|**Descrizione**|
|:-----|:-----|
|Tipo di messaggio| Il tipo di messaggio da cercare. Corrisponde alla proprietà della posta elettronica Kind (Tipo). Valori possibili:  <br/><br/>  contatti  <br/>  documenti  <br/>  email  <br/>  externaldata  <br/>  fax  <br/>  im  <br/>  riviste  <br/>  riunioni  <br/>  microsoftteams  <br/>  Note  <br/>  messaggi  <br/>  rssfeeds  <br/>  attività  <br/>  Voicemail|
|Partecipanti|Tutti i campi persone in un messaggio di posta elettronica. Questi campi sono da, a, CC e Ccn.|
|Tipo|La proprietà della classe Message per un elemento di posta elettronica. Questa è la stessa proprietà della proprietà di posta elettronica di ItemClass. È anche una condizione multivalore. In questo modo, per selezionare più classi messaggio, tenere premuto il tasto **CTRL** e fare clic su due o più classi di messaggi nell'elenco a discesa che si desidera aggiungere alla condizione. Ogni classe del messaggio selezionata nell'elenco verrà connessa logicamente dall'operatore **or** nella query di ricerca corrispondente.  <br/> Per un elenco delle classi di messaggi (e l'ID di classe del messaggio corrispondente) che vengono utilizzate da Exchange e che è possibile selezionare nell'elenco delle classi dei **messaggi** , vedere [tipi di elementi e classi di messaggi](https://go.microsoft.com/fwlink/?linkid=848143).|
|Ricevuto|La data in cui un messaggio di posta elettronica viene ricevuto da un destinatario. Corrisponde alla proprietà della posta elettronica Received (Ricevuto).|
|Destinatari|Tutti i campi dei destinatari in un messaggio di posta elettronica. Questi campi sono a, CC e Ccn.|
|Mittente|Il mittente di un messaggio di posta elettronica.|
|Inviati|La data in cui un messaggio di posta elettronica viene inviato dal mittente. Corrisponde alla proprietà della posta elettronica Sent (Inviato).|
|Oggetto|Il testo nella riga dell'oggetto di un messaggio di posta elettronica.|
|A|Il destinatario di un messaggio di posta elettronica nel campo a.|
|||
  
### <a name="conditions-for-document-properties"></a>Condizioni per le proprietà dei documenti

Creare una condizione utilizzando le proprietà del documento per la ricerca di documenti nei siti di SharePoint e OneDrive for business. Nella tabella seguente vengono elencate le proprietà dei documenti che è possibile utilizzare per una condizione. Queste proprietà sono un sottoinsieme delle proprietà del sito descritte in precedenza. Queste descrizioni vengono ripetute per la vostra convenienza.
  
|**Condizione**|**Descrizione**|
|:-----|:-----|
|Author|Il campo dell'autore dei documenti di Office, che persiste se un documento viene copiato. Ad esempio, se un utente crea un documento e lo invia tramite posta elettronica a qualcun altro che lo carica in SharePoint, il documento conserva comunque l'autore originale.|
|Titolo|Il titolo del documento. La proprietà Title è rappresentata dai metadati specificati nei documenti di Office. È diverso dal nome di file del documento.|
|Creato|La data di creazione di un documento.|
|Data ultima modifica|La data dell'ultima modifica di un documento.|
|Tipo file|L'estensione di un file; ad esempio, docx, 1, pptx o xlsx. Corrisponde alla proprietà dei siti FileExtension.|
|||
  
### <a name="operators-used-with-conditions"></a>Operatori utilizzati con condizioni

When you add a condition, you can select an operator that is relevant to type of property for the condition. The following table describes the operators that are used with conditions and lists the equivalent that is used in the search query.
  
|**Operatore**|**Equivalente nella query**|**Descrizione**|
|:-----|:-----|:-----|
|Dopo|`property>date`|Used with date conditions. Returns items that were sent, received, or modified after the specified date.|
|Prima|`property<date`|Used with date conditions. Returns items that were sent, received, or modified before the specified date.|
|Tra|`date..date`|Utilizzato con condizioni relative alla data e alla dimensione. Se utilizzato con una condizione relativa alla data, restituisce gli elementi che sono stati inviati, ricevuti o modificati entro l'intervallo di date specificato. Se utilizzato con una condizione relativa alla dimensione, restituisce gli elementi di dimensioni comprese nell'intervallo specificato.|
|Contains any of|`(property:value) OR (property:value)`|Utilizzato con condizioni per le proprietà che specificano un valore di stringa. Restituisce gli elementi che contengono una parte qualsiasi di uno o più valori di stringa specificati.|
|Doesn't contain any of|`-property:value`  <br/> `NOT property:value`|Utilizzato con condizioni per le proprietà che specificano un valore di stringa. Restituisce gli elementi che non contengono parti del valore di stringa specificato.|
|Doesn't equal any of|`-property=value`  <br/> `NOT property=value`|Used with conditions for properties that specify a string value. Returns items that don't contain the specific string.|
|È uguale a|`size=value`|Restituisce gli elementi equivalenti alla dimensione specificata. <sup>1</sup>|
|Equals any of|`(property=value) OR (property=value)`|Used with conditions for properties that specify a string value. Returns items that are an exact match of one or more specified string values.|
|Maggiore|`size>value`|Restituisce gli elementi in cui la proprietà specificata è maggiore del valore specificato. <sup>1</sup>|
|Greater or equal|`size>=value`|Restituisce gli elementi in cui la proprietà specificata è maggiore o uguale al valore specificato. <sup>1</sup>|
|Meno|`size<value`|Restituisce gli elementi che sono maggiori o uguali al valore specifico. <sup>1</sup>|
|Less or equal|`size<=value`|Restituisce gli elementi che sono maggiori o uguali al valore specifico. <sup>1</sup>|
|Not equal|`size<>value`|Restituisce gli elementi che non sono uguali alle dimensioni specificate. <sup>1</sup>|
|||
   
> [!NOTE]
> <sup>1</sup> questo operatore è disponibile solo per le condizioni che utilizzano la proprietà Size. 
  
### <a name="guidelines-for-using-conditions"></a>Linee guida per l'uso di condizioni

Tenere presente quanto segue quando si utilizzano le condizioni di ricerca.
  
- Una condizione è collegata logicamente alla query con parola chiave (specificata nella relativa casella) dall'operatore **AND**. Ciò significa che, per essere inclusi nei risultati, gli elementi devono soddisfare sia la query con parola chiave, sia la condizione. Ecco come le condizioni consentono di circoscrivere i risultati. 
    
- Se si aggiungono due o più condizioni univoche a una query di ricerca (condizioni che specificano proprietà diverse), tali condizioni sono connesse logicamente dall'operatore **and** . Ciò significa che vengono restituiti solo gli elementi che soddisfano tutte le condizioni (oltre alle query con parole chiave). 
    
- Se si aggiunge più di una condizione per la stessa proprietà, tali condizioni vengono collegate logicamente dall'operatore **OR**. Ciò significa che vengono restituiti gli elementi che soddisfano la query con parola chiave e una delle condizioni. Pertanto, i gruppi con le stesse condizioni vengono collegati tra loro dall'operatore **OR**, quindi gli insiemi di condizioni univoche vengono collegati dall'operatore **AND**. 
    
- Se si aggiungono più valori, separati da virgole o da due punti a una singola condizione, tali valori sono connessi dall'operatore **or** . Ciò significa che gli elementi vengono restituiti se contengono uno dei valori specificati per la proprietà nella condizione. 
    
- La query di ricerca creata utilizzando la casella e le condizioni delle parole chiave viene visualizzata nella pagina di **ricerca** , nel riquadro dei dettagli per la ricerca selezionata. In una query, tutto a destra della notazione indica le `(c:c)` condizioni che sono state aggiunte alla query. 
    
- Le condizioni aggiungono solo le proprietà alla query di ricerca, non gli operatori. Questo è il motivo per cui la query visualizzata nel riquadro dei dettagli non Mostra gli operatori a destra della `(c:c)` notazione. KQL aggiunge gli operatori logici (in base alle regole illustrate in precedenza) quando viene eseguita la query. 
    
- È possibile utilizzare il controllo di trascinamento della selezione per risequenziare l'ordine delle condizioni. Fare clic sul controllo per una condizione e spostarla verso l'alto o verso il basso.
    
- Come descritto in precedenza, alcune proprietà delle condizioni consentono di digitare più valori. I valori sono collegati logicamente dall'operatore **OR**. Ne consegue che la stessa logica dispone di più istanze della stessa condizione, ognuna con un singolo valore. Nelle illustrazioni seguenti viene mostrato un esempio di una singola condizione con più valori e un esempio di più condizioni (per la stessa proprietà) con un singolo valore. Entrambi gli esempi determinano la stessa query:`(filetype="docx") OR (filetype="pptx") OR (filetype="xlsx")`
    
    ![Una condizione con più valori](../media/9880aa29-d117-4531-be20-6d53f1d21341.gif)
  
    ![Più condizioni di ricerca per la stessa proprietà](../media/1e63d37d-6d8d-4c9b-a509-a7e1c3a05193.gif)
  
> [!TIP]
> If a condition accepts multiple values, we recommend that you use a single condition and specify multiple values (separated by commas or semi-colons). This helps ensure the query logic that's applied is what you intend. 
  
### <a name="examples-of-using-conditions-in-search-queries"></a>Esempi

Negli esempi seguenti viene illustrata la versione basata su GUI di una query di ricerca con condizioni, la sintassi delle query di ricerca che viene visualizzata nel riquadro dei dettagli della ricerca selezionata (restituita anche dal cmdlet **Get-ComplianceSearch** ) e la logica della query KQL corrispondente. 
  
#### <a name="example-1"></a>Esempio 1

In questo esempio vengono restituiti i documenti sui siti di SharePoint e OneDrive for business che contengono un numero di carta di credito e sono stati modificati per l'ultima volta il 1 ° gennaio 2016.
  
 **GUI**
  
![Primo esempio relativo alle condizioni di ricerca](../media/099515ba-d4ee-474e-af25-3aa48816b87b.gif)
  
 **Sintassi della query di ricerca**
  
 `SensitiveType:"Credit Card Number"(c:c)(lastmodifiedtime<2016-01-01)`
  
 **Logica della query di ricerca**
  
 `SensitiveType:"Credit Card Number" AND (lastmodifiedtime<2016-01-01)`
  
#### <a name="example-2"></a>Esempio 2

This example returns email items or documents that contain the keyword "report", that were sent or created before April 1, 2105, and that contain the word "northwind" in the subject field of email messages or in the title property of documents. The query excludes Web pages that meet the other search criteria.
  
 **GUI**
  
![Secondo esempio relativo alle condizioni di ricerca](../media/fe07d495-df81-42da-8106-3cdb409c6e7f.gif)
  
 **Sintassi della query di ricerca**
  
 `report(c:c)(date<2016-04-01)(subjecttitle:"northwind")(-filetype="aspx")`
  
 **Logica della query di ricerca**
  
 `report AND (date<2016-04-01) AND (subjecttitle:"northwind") NOT (filetype="aspx")`
  
#### <a name="example-3"></a>Esempio 3

In questo esempio vengono restituiti i messaggi di posta elettronica o le riunioni del calendario inviate tra 12/1/2016 e 11/30/2016 e che contengono parole che iniziano con "Phone" o "smartphone".
  
 **GUI**
  
![Terzo esempio relativo alle condizioni di ricerca](../media/973d45fc-0923-43d6-9d0a-25e4a625f057.gif)
  
 **Sintassi della query di ricerca**
  
 `phone* OR smartphone*(c:c)(sent=2016-12-01..2016-11-30)(kind="email")(kind="meetings")`
  
 **Logica della query di ricerca**
  
 `phone* OR smartphone* AND (sent=2016-12-01..2016-11-30) AND ((kind="email") OR (kind="meetings"))`
  
## <a name="special-characters"></a>Caratteri speciali

Alcuni caratteri speciali non sono inclusi nell'indice di ricerca e pertanto non sono disponibili per la ricerca. Questo include anche i caratteri speciali che rappresentano gli operatori di ricerca nella query di ricerca. Ecco un elenco di caratteri speciali che sono stati sostituiti da uno spazio vuoto nella query di ricerca effettiva o che causano un errore di ricerca.

`+ - = : ! @ # % ^ & ; _ / ? ( ) [ ] { }`

## <a name="searching-for-site-content-shared-with-external-users"></a>Ricerca di contenuti dei siti condivisi con utenti esterni

È inoltre possibile utilizzare la funzionalità Ricerca contenuto nel centro sicurezza & conformità per cercare i documenti archiviati nei siti di SharePoint e OneDrive for business che sono stati condivisi con utenti esterni all'organizzazione. Ciò consente di identificare informazioni proprietarie o sensibili condivise all'esterno dell'organizzazione. È possibile eseguire questa operazione utilizzando la `ViewableByExternalUsers` Proprietà in una query di parole chiave. Questa proprietà restituisce documenti o siti che sono stati condivisi con utenti esterni utilizzando uno dei metodi di condivisione seguenti: 
  
- Un invito alla condivisione che richiede agli utenti di accedere all'organizzazione come utente autenticato.
    
- Un collegamento Guest Anonimo, che consente a tutti gli utenti che dispongono di questo collegamento di accedere alla risorsa senza dover essere autenticati.
    
Ecco alcuni esempi:
  
- La query `ViewableByExternalUsers:true AND SensitiveType:"Credit Card Number"` restituisce tutti gli elementi che sono stati condivisi con utenti esterni all'organizzazione e che contengono un numero di carta di credito. 
    
- La query `ViewableByExternalUsers:true AND ContentType:document AND site:"https://contoso.sharepoint.com/Sites/Teams"` restituisce un elenco di documenti in tutti i siti del team nell'organizzazione che sono stati condivisi con utenti esterni. 
    
> [!TIP]
> Una query di ricerca, ad esempio, `ViewableByExternalUsers:true AND ContentType:document` potrebbe restituire numerosi file con estensione aspx nei risultati della ricerca. Per eliminare questi (o altri tipi di file), è possibile utilizzare la `FileExtension` proprietà per escludere tipi di file specifici, ad esempio `ViewableByExternalUsers:true AND ContentType:document NOT FileExtension:aspx` . 
  
Che cosa viene considerato come contenuto condiviso con persone esterne all'organizzazione? Documenti nei siti di SharePoint e OneDrive for business dell'organizzazione condivisi mediante l'invio di un invito alla condivisione o condivisi in posizioni pubbliche. Ad esempio, le attività utente seguenti determinano il contenuto visualizzabile dagli utenti esterni:
  
- Un utente condivide un file o una cartella con una persona esterna all'organizzazione.
    
- Un utente crea e invia un collegamento a un file condiviso a una persona esterna all'organizzazione. Questo collegamento consente all'utente esterno di visualizzare (o modificare) il file.
    
- Un utente invia un invito alla condivisione o un collegamento guest a una persona esterna all'organizzazione per visualizzare (o modificare) un file condiviso.
    
### <a name="issues-using-the-viewablebyexternalusers-property"></a>Problemi relativi all'utilizzo della proprietà ViewableByExternalUsers

Mentre la `ViewableByExternalUsers` proprietà rappresenta lo stato del fatto che un documento o un sito sia condiviso con utenti esterni, sono presenti alcune avvertenze su ciò che questa proprietà fa e non riflette. Negli scenari seguenti, il valore della `ViewableByExternalUsers` proprietà non verrà aggiornato e i risultati di una query di ricerca del contenuto che utilizza questa proprietà potrebbero non essere corretti. 
  
- Modifiche apportate ai criteri di condivisione, ad esempio la disattivazione della condivisione esterna per un sito o per l'organizzazione. La proprietà continuerà a visualizzare documenti condivisi in precedenza come accessibili esternamente anche se l'accesso esterno potrebbe essere stato revocato.
    
- Modifiche apportate all'appartenenza a un gruppo, ad esempio l'aggiunta o la rimozione di utenti esterni a gruppi Microsoft 365 o gruppi di sicurezza di Microsoft 365. La proprietà non verrà aggiornata automaticamente per gli elementi a cui il gruppo ha accesso.
    
- Invio di inviti di condivisione a utenti esterni in cui il destinatario non ha accettato l'invito e pertanto non ha ancora accesso al contenuto.
    
In questi scenari, la `ViewableByExternalUsers` proprietà non riflette lo stato di condivisione corrente finché il sito o la raccolta documenti non viene sottoposta a ricerca per indicizzazione e reindicizzato. 

## <a name="searching-for-site-content-shared-within-your-organization"></a>Ricerca di contenuto del sito condiviso all'interno dell'organizzazione

Come spiegato in precedenza, è possibile utilizzare la `SharedWithUsersOWSUser` Proprietà in modo da cercare i documenti condivisi tra gli utenti dell'organizzazione. Quando una persona condivide un file (o una cartella) con un altro utente all'interno dell'organizzazione, viene visualizzato un collegamento al file condiviso nella pagina **condivisi con me** nell'account OneDrive for business della persona con cui è stato condiviso il file. Ad esempio, per cercare i documenti che sono stati condivisi con Sara Davis, è possibile utilizzare la query `SharedWithUsersOWSUser:"sarad@contoso.com"` . Se si esportano i risultati di questa ricerca, verranno scaricati i documenti originali (che si trovano nel percorso del contenuto della persona che ha condiviso i documenti con Sara).
  
I documenti devono essere condivisi in modo esplicito con un utente specifico da restituire nei risultati della ricerca quando si utilizza la `SharedWithUsersOWSUser` Proprietà. Ad esempio, quando una persona condivide un documento nel proprio account OneDrive, ha la possibilità di condividerlo con chiunque (all'interno o all'esterno dell'organizzazione), condividerlo solo con persone all'interno dell'organizzazione oppure condividerlo con una persona specifica. Di seguito è riportata una schermata **della finestra di condivisione in** OneDrive, in cui vengono visualizzate le tre opzioni di condivisione. 
  
![Solo i file condivisi con persone specifiche verranno restituiti da una query di ricerca che utilizza la proprietà SharedWithUsersOWSUser](../media/469a4b61-68bd-4ab0-b612-ab6302973886.png)
  
Solo i documenti condivisi tramite la terza opzione (condivisi con **persone specifiche**) verranno restituiti da una query di ricerca che utilizza la `SharedWithUsersOWSUser` Proprietà. 

## <a name="searching-for-skype-for-business-conversations"></a>Ricerca di conversazioni di Skype for business

È possibile utilizzare la query di parole chiave seguente per cercare in modo specifico il contenuto nelle conversazioni di Skype for business:

```powershell
kind:im
```

La query di ricerca precedente restituisce anche chat da Microsoft teams. Per evitare questo risultato, è possibile restringere i risultati della ricerca per includere solo le conversazioni di Skype for business utilizzando la seguente query di parole chiave:

```powershell
kind:im AND subject:conversation
```

La query con parole chiave precedente esclude le chat in Microsoft teams perché le conversazioni di Skype for business vengono salvate come messaggi di posta elettronica con una riga dell'oggetto che inizia con la parola "Conversation".

Per cercare le conversazioni di Skype for business che si sono verificate in un intervallo di date specifico, utilizzare la seguente query di parole chiave:

```powershell
kind:im AND subject:conversation AND (received=startdate..enddate)
```

## <a name="search-tips-and-tricks"></a>Suggerimenti pratici per la ricerca

- Le ricerche di parole chiave non sono maiuscole/minuscole. Ad esempio, **cat** e **CAT** restituiscono gli stessi risultati. 

- Gli operatori booleani **e**, **o**, **No**, e **vicino** devono essere maiuscoli. 

- Uno spazio compreso tra due parole chiave o due `property:value` espressioni equivale all'utilizzo **di e**. Ad esempio, `from:"Sara Davis" subject:reorganization` restituisce tutti i messaggi inviati da Sara Davis che contengono la riorganizzazione di parole nella riga dell'oggetto. 

- Utilizzare la sintassi che corrisponde al `property:value` formato. I valori non sono distinzione tra maiuscole e minuscole e non possono avere uno spazio dopo l'operatore. Se esiste uno spazio, il valore previsto sarà una ricerca full-text. Ad esempio `to: pilarp` , la ricerca di "pilarp" viene eseguita come parola chiave anziché per i messaggi inviati a pilarp. 

- When searching a recipient property, such as To, From, Cc, or Recipients, you can use an SMTP address, alias, or display name to denote a recipient. For example, you can use pilarp@contoso.com, pilarp, or "Pilar Pinilla".

- È possibile utilizzare solo le ricerche con caratteri jolly prefix. ad esempio, **Cat \* ** o **set \* **. Le ricerche suffisso (** \* Cat**), le ricerche infissi (**c \* t**) e le ricerche di sottostringhe (** \* Cat \* **) non sono supportate.

- Quando si esegue la ricerca di una proprietà, utilizzare le virgolette doppie ("") se il valore di ricerca è costituito da più parole. Ad esempio `subject:budget Q1` , vengono restituiti messaggi che contengono **budget** nella riga dell'oggetto e che contengono **Q1** in qualsiasi punto del messaggio o in una delle proprietà del messaggio. Se si utilizza `subject:"budget Q1"` restituisce tutti i messaggi che contengono **budget Q1** in qualsiasi punto della riga dell'oggetto.

- Per escludere i contenuti contrassegnati con un determinato valore della proprietà dai risultati della ricerca, inserire un segno meno (-) prima del nome della proprietà. Ad esempio, `-from:"Sara Davis"` esclude tutti i messaggi inviati da Sara Davis.

- È possibile esportare gli elementi in base al tipo di messaggio. Ad esempio, per esportare conversazioni e chat di Skype in Microsoft teams, utilizzare la sintassi `kind:im` . Per restituire solo i messaggi di posta elettronica, è necessario utilizzare `kind:email` . Per restituire le chat, le riunioni e le chiamate in Microsoft teams, utilizzare `kind:microsoftteams` .
