---
title: Query con parole chiave e condizioni di ricerca per eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
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
description: Informazioni sulle proprietà di posta elettronica e file che è possibile cercare utilizzando gli strumenti di ricerca di eDiscovery in Microsoft 365.
ms.openlocfilehash: 390477012c6a2a57c5e305641ba5b79ff10f4ea7
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538436"
---
# <a name="keyword-queries-and-search-conditions-for-ediscovery"></a>Query con parole chiave e condizioni di ricerca per eDiscovery

In questo argomento vengono descritte le proprietà di posta elettronica e documento che è possibile cercare negli elementi di posta elettronica e nelle conversazioni di chat di Microsoft Teams in Exchange Online e i documenti archiviati nei siti SharePoint e OneDrive for Business utilizzando gli strumenti di ricerca eDiscovery nel Centro conformità Microsoft 365. Ciò include Ricerca contenuto, Core eDiscovery e Advanced eDiscovery (le ricerche eDiscovery in Advanced eDiscovery sono denominate *raccolte).* È inoltre possibile utilizzare i cmdlet **\* -ComplianceSearch** in PowerShell & Centro sicurezza e conformità per cercare queste proprietà. L'argomento descrive anche:
  
- Utilizzo di operatori di ricerca booleani, condizioni di ricerca e altre tecniche di query di ricerca per affinare i risultati della ricerca.

- Ricerca di tipi di dati sensibili e tipi di dati sensibili personalizzati in SharePoint e OneDrive for Business.

- Ricerca di contenuto del sito condiviso con utenti esterni all'organizzazione

Per istruzioni dettagliate su come creare ricerche eDiscovery diverse, vedere:

- [Ricerca contenuto](content-search.md)

- [Cercare contenuto in Core eDiscovery](search-for-content-in-core-ediscovery.md)

- [Creare una raccolta di bozze in Advanced eDiscovery](create-draft-collection.md)

> [!NOTE]
> Le ricerche eDiscovery nel Centro conformità Microsoft 365 e i cmdlet **\* -ComplianceSearch** corrispondenti in & PowerShell del Centro sicurezza e conformità utilizzano il linguaggio KQL (Keyword Query Language). Per informazioni più dettagliate, vedere [Keyword Query Language syntax reference](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).
  
## <a name="searchable-email-properties"></a>Proprietà di posta elettronica disponibili per la ricerca

Nella tabella seguente sono elencate le proprietà dei messaggi di posta elettronica che è possibile cercare utilizzando gli strumenti di ricerca di eDiscovery nel Centro conformità Microsoft 365 o utilizzando il cmdlet **New-ComplianceSearch** o **Set-ComplianceSearch.** La tabella include un esempio della sintassi  _property:value_ per ogni proprietà e una descrizione dei risultati della ricerca restituiti dagli esempi. È possibile digitare queste  `property:value` coppie nella casella delle parole chiave per una ricerca eDiscovery. 

> [!NOTE]
> Quando si cercano proprietà di posta elettronica, non è possibile cercare elementi in cui la proprietà specificata è vuota o vuota. Ad esempio, l'utilizzo della coppia *property:value* di **subject:""** per cercare messaggi di posta elettronica con una riga dell'oggetto vuota restituirà zero risultati. Ciò vale anche per la ricerca di proprietà di siti e contatti.
  
| Proprietà | Descrizione proprietà | Esempi | Risultati di ricerca restituiti dagli esempi |
|:-----|:-----|:-----|:-----|
|AttachmentNames|I nomi dei file allegati a un messaggio di posta elettronica.|`attachmentnames:annualreport.ppt`  <br/> `attachmentnames:annual*` <br/> `attachmentnames:.pptx` |Messaggi che contengono un file allegato denominato annualreport.ppt. Nel secondo esempio, l'utilizzo del carattere jolly ( * ) restituisce i messaggi con la parola "annual" nel nome file di un allegato. Nel terzo esempio vengono restituiti tutti gli allegati con estensione pptx.|
|Ccn|Campo Ccn di un messaggio di posta elettronica. <sup>1</sup>|`bcc:pilarp@contoso.com`  <br/> `bcc:pilarp`  <br/> `bcc:"Pilar Pinilla"`|Tutti gli esempi restituiscono messaggi contenenti Pilar Pinilla nel campo Bcc (Ccn).|
|Categoria| Le categorie da cercare. Le categorie possono essere definite dagli utenti utilizzando Outlook o Outlook sul Web (in precedenza noto come Outlook Web App). I valori possibili sono i seguenti:  <br/><br/>  blu  <br/>  verde  <br/>  arancione  <br/>  viola  <br/>  rosso  <br/>  giallo|`category:"Red Category"`|I messaggi ai quali è stata assegnata la categoria di colore rosso nelle cassette postali di origine. |
|Cc|Campo Cc di un messaggio di posta elettronica. <sup>1</sup>|`cc:pilarp@contoso.com`  <br/> `cc:"Pilar Pinilla"`|In entrambi gli esempi, i messaggi con Pilar Pinilla specificato nel campo Cc.|
|Folderid|ID cartella (GUID) di una cartella della cassetta postale specifica. Se si utilizza questa proprietà, assicurarsi di cercare nella cassetta postale in cui si trova la cartella specificata. Verrà cercata solo la cartella specificata. Le sottocartelle nella cartella non verranno cercate. Per cercare le sottocartelle, è necessario utilizzare la proprietà Folderid per la sottocartella in cui si desidera eseguire la ricerca.  <br/> Per ulteriori informazioni sulla ricerca della proprietà Folderid e sull'utilizzo di uno script per ottenere gli ID cartella per una cassetta postale specifica, vedere [Use Content search for targeted collections](use-content-search-for-targeted-collections.md).|`folderid:4D6DD7F943C29041A65787E30F02AD1F00000000013A0000`  <br/> `folderid:2370FB455F82FC44BE31397F47B632A70000000001160000 AND participants:garthf@contoso.com`|Nel primo esempio vengono restituiti tutti gli elementi nella cartella della cassetta postale specificata. Nel secondo esempio vengono restituiti tutti gli elementi nella cartella della cassetta postale specificata inviati o ricevuti da garthf@contoso.com.|
|Da|Mittente di un messaggio di posta elettronica. <sup>1</sup>|`from:pilarp@contoso.com`  <br/> `from:contoso.com`|I messaggi inviati dall'utente specificato o da un dominio specificato.|
|HasAttachment|Indica se un messaggio ha un allegato. Utilizzare i valori **true** o **false**.|`from:pilar@contoso.com AND hasattachment:true`|Messaggi inviati dall'utente specificato con allegati.|
|Priorità|La priorità di un messaggio di posta elettronica, che può essere specificata dall'utente al momento dell'invio di un messaggio. Per impostazione predefinita, i messaggi vengono inviati con una priorità normale, a meno che il mittente non imposti la priorità **high** (alta) o **low** (bassa).|`importance:high`  <br/> `importance:medium`  <br/> `importance:low`|I messaggi contrassegnati con priorità alta, media o bassa.|
|IsRead|Indica se i messaggi sono stati letti. Utilizzare i valori **true** o **false**.|`isread:true`  <br/> `isread:false`|Nel primo esempio vengono restituiti i messaggi con la proprietà IsRead impostata su **True.** Nel secondo esempio vengono restituiti i messaggi con la proprietà IsRead impostata su **False.**|
|Itemclass|Utilizzare questa proprietà per cercare tipi di dati di terze parti specifici importati dall'organizzazione Office 365. Utilizzare la sintassi seguente per questa proprietà:  `itemclass:ipm.externaldata.<third-party data type>*`|`itemclass:ipm.externaldata.Facebook* AND subject:contoso`  <br/> `itemclass:ipm.externaldata.Twitter* AND from:"Ann Beebe" AND "Northwind Traders"`|Nel primo esempio vengono restituiti gli elementi di Facebook che contengono la parola "contoso" nella proprietà Subject. Nel secondo esempio vengono restituiti gli elementi di Twitter pubblicati da Ann Beebe e che contengono la parola chiave "Northwind Traders".  <br/> Per un elenco completo dei valori da utilizzare per i tipi di dati di terze parti per la proprietà ItemClass, vedere [Use Content search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md).|
|Kind| Tipo di messaggio di posta elettronica da cercare. Valori possibili:  <br/>  contatti  <br/>  docs  <br/>  e-mail  <br/>  externaldata  <br/>  fax  <br/>  im  <br/>  journals  <br/>  riunioni  <br/>  microsoftteams (restituisce elementi da chat, riunioni e chiamate in Microsoft Teams)  <br/>  note  <br/>  post  <br/>  rssfeeds  <br/>  attività  <br/>  segreteria telefonica|`kind:email`  <br/> `kind:email OR kind:im OR kind:voicemail`  <br/> `kind:externaldata`|Nel primo esempio vengono restituiti i messaggi di posta elettronica che soddisfano i criteri di ricerca. Nel secondo esempio vengono restituiti i messaggi di posta elettronica, le conversazioni di messaggistica istantanea (incluse Skype for Business conversazioni e chat in Microsoft Teams) e i messaggi vocali che soddisfano i criteri di ricerca. Nel terzo esempio vengono restituiti gli elementi importati nelle cassette postali di Microsoft 365 da origini dati di terze parti, ad esempio Twitter, Facebook e Cisco Jabber, che soddisfano i criteri di ricerca. Per ulteriori informazioni, vedere [Archiving third-party data in Office 365](https://www.microsoft.com/?ref=go).|
|Partecipanti|Tutti i campi delle persone in un messaggio di posta elettronica. Questi campi sono From, To, Cc e Bcc.<sup>1</sup>|`participants:garthf@contoso.com`  <br/> `participants:contoso.com`|I messaggi inviati da o a garthf@contoso.com. Il secondo esempio restituisce tutti i messaggi inviati da o a un utente nel dominio contoso.com.|
|Ricevuto|La data in cui un messaggio di posta elettronica viene ricevuto da un destinatario.|`received:04/15/2016`  <br/> `received>=01/01/2016 AND received<=03/31/2016`|Messaggi ricevuti il 15 aprile 2016. Nel secondo esempio vengono restituiti tutti i messaggi ricevuti tra il 1° gennaio 2016 e il 31 marzo 2016.|
|Destinatari|Tutti i campi dei destinatari in un messaggio di posta elettronica. Questi campi sono A, Cc e Ccn.<sup>1</sup>|`recipients:garthf@contoso.com`  <br/> `recipients:contoso.com`|I messaggi inviati a garthf@contoso.com. Il secondo esempio restituisce i messaggi inviati ai destinatari nel dominio contoso.com.|
|Inviato|La data in cui un messaggio di posta elettronica viene inviato dal mittente.|`sent:07/01/2016`  <br/> `sent>=06/01/2016 AND sent<=07/01/2016`|I messaggi inviati in una data specifica o entro l'intervallo di date specificato.|
|Dimensioni|Le dimensioni di un elemento, in byte.|`size>26214400`  <br/> `size:1..1048567`|I messaggi di dimensioni maggiori di 25 MB. Il secondo esempio restituisce i messaggi di dimensioni comprese tra 1 e 1.048.567 byte (1 MB).|
|Oggetto|Il testo nella riga dell'oggetto di un messaggio di posta elettronica.  <br/> **Nota:** Quando si utilizza la proprietà Subject in una query, la ricerca restituisce tutti i messaggi in cui la riga dell'oggetto contiene il testo che si sta cercando. In altre parole, la query non restituisce solo i messaggi che hanno una corrispondenza esatta. Ad esempio, se si cerca , i risultati includeranno i messaggi con oggetto  `subject:"Quarterly Financials"` "Quarterly Financials 2018".|`subject:"Quarterly Financials"`  <br/> `subject:northwind`|Messaggi che contengono la frase "Quarterly Financials" in qualsiasi punto del testo della riga dell'oggetto. Il secondo esempio restituisce tutti i messaggi che contengono la parola northwind nella riga dell'oggetto.|
|A|Campo A di un messaggio di posta elettronica. <sup>1</sup>|`to:annb@contoso.com`  <br/> `to:annb ` <br/> `to:"Ann Beebe"`|Tutti gli esempi restituiscono i messaggi in cui è specificato l'utente Ann Beebe nella riga To: (A:).|
|||||
   
> [!NOTE]
> <sup>1</sup> Per il valore di una proprietà del destinatario, è possibile utilizzare l'indirizzo di posta elettronica (denominato anche nome principale utente o UPN), il nome visualizzato o l'alias per specificare un utente.  Ad esempio, è possibile usare annb@contoso.com, annb o "Ann Beebe" per specificare l'utente Ann Beebe.

### <a name="recipient-expansion"></a>Espansione dei destinatari

Quando si esegue una ricerca in una delle proprietà del destinatario (Da, A, Cc, Ccn, Partecipanti e Destinatari), Microsoft 365 tenta di espandere l'identità di ogni utente cercandoli in Azure Active Directory (Azure AD).  Se l'utente viene trovato in Azure AD, la query viene espansa in modo da includere l'indirizzo di posta elettronica (o UPN) dell'utente, l'alias, il nome visualizzato e LegacyExchangeDN. Ad esempio, una query, ad `participants:ronnie@contoso.com` esempio, si espande in `participants:ronnie@contoso.com OR participants:ronnie OR participants:"Ronald Nelson" OR participants:"<LegacyExchangeDN>"` .

Per impedire l'espansione dei destinatari, aggiungere un carattere jolly (asterisco) alla fine dell'indirizzo di posta elettronica e utilizzare un nome di dominio ridotto. Ad esempio, `participants:"ronnie@contoso*"` assicurati di racchiudere l'indirizzo di posta elettronica tra virgolette doppie.

Tenere tuttavia presente che se si impedisce l'espansione dei destinatari nella query di ricerca, è possibile che gli elementi pertinenti non vengano restituiti nei risultati della ricerca. I messaggi di posta Exchange possono essere salvati con formati di testo diversi nei campi dei destinatari. L'espansione del destinatario ha lo scopo di attenuare questo problema tramite la restituzione di messaggi che potrebbero contenere formati di testo diversi. Pertanto, se si impedisce l'espansione dei destinatari, la query di ricerca potrebbe non restituire tutti gli elementi che potrebbero essere rilevanti per l'indagine.

> [!NOTE]
> Se è necessario esaminare o ridurre gli elementi restituiti da una query di ricerca a causa dell'espansione dei destinatari, è consigliabile utilizzare Advanced eDiscovery. È possibile cercare i messaggi (sfruttando l'espansione dei destinatari), aggiungerli a un set di recensioni e quindi utilizzare query o filtri del set di revisione per esaminare o limitare i risultati. Per ulteriori informazioni, vedere [Collect data for a case](collecting-data-for-ediscovery.md) ed Query the data in a review [set.](review-set-search.md)

## <a name="searchable-site-properties"></a>Proprietà dei siti disponibili per la ricerca

Nella tabella seguente sono elencate alcune delle proprietà di SharePoint e OneDrive for Business che possono essere ricercate utilizzando gli strumenti di ricerca eDiscovery nel Centro conformità Microsoft 365 o utilizzando il cmdlet **New-ComplianceSearch** o **Set-ComplianceSearch.** La tabella include un esempio della sintassi  _property:value_ per ogni proprietà e una descrizione dei risultati della ricerca restituiti dagli esempi. 
  
Per un elenco completo delle SharePoint disponibili per la ricerca, vedere [Overview of crawled and managed properties in SharePoint](/SharePoint/technical-reference/crawled-and-managed-properties-overview). È possibile eseguire ricerche  nelle **proprietà** contrassegnate con Sì nella colonna Queryable.
  
| Proprietà | Descrizione proprietà | Esempio | Risultati di ricerca restituiti dagli esempi |
|:-----|:-----|:-----|:-----|
|Author|Il campo dell'autore dei documenti di Office, che persiste se un documento viene copiato. Ad esempio, se un utente crea un documento e lo invia tramite posta elettronica a un altro utente che lo carica SharePoint, il documento conserverà comunque l'autore originale. Assicurati di usare il nome visualizzato dell'utente per questa proprietà.|`author:"Garth Fort"`|Tutti i documenti creati da Garth Fort.|
|ContentType|Tipo SharePoint contenuto di un elemento, ad esempio Elemento, Documento o Video.|`contenttype:document`|Vengono restituiti tutti i documenti.|
|Creato|La data di creazione di un elemento.|`created>=06/01/2016`|Tutti gli elementi creati il 1° giugno 2016 o dopo il 1° giugno 2016.|
|CreatedBy|L'utente che ha creato o caricato un elemento. Assicurati di usare il nome visualizzato dell'utente per questa proprietà.|`createdby:"Garth Fort"`|Tutti gli elementi creati o caricati da Garth Fort.|
|DetectedLanguage|La lingua di un elemento.|`detectedlanguage:english`|Tutti gli elementi in lingua inglese.|
|DocumentLink|Percorso (URL) di una cartella specifica in un SharePoint o OneDrive for Business sito. Se si utilizza questa proprietà, assicurarsi di cercare il sito in cui si trova la cartella specificata.  <br/> Per restituire gli elementi contenuti nelle sottocartelle della cartella specificata per la proprietà documentlink, è necessario aggiungere / all'URL della cartella specificata, ad \* esempio,  `documentlink: "https://contoso.sharepoint.com/Shared Documents/*"`  <br/> <br/>Per ulteriori informazioni sulla ricerca della proprietà documentlink e sull'utilizzo di uno script per ottenere gli URL documentlink per le cartelle in un sito specifico, vedere [Use Content search for targeted collections](use-content-search-for-targeted-collections.md).|`documentlink:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Private"`  <br/> `documentlink:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Shared with Everyone/*" AND filename:confidential`|Nel primo esempio vengono restituiti tutti gli elementi nella cartella OneDrive for Business specificata. Nel secondo esempio vengono restituiti i documenti nella cartella del sito specificata (e in tutte le sottocartelle) che contengono la parola "confidential" nel nome del file.|
|FileExtension|Estensione di un file. ad esempio docx, one, pptx o xlsx.|`fileextension:xlsx`|Tutti Excel file (Excel 2007 e versioni successive)|
|FileName|Il nome di un file.|`filename:"marketing plan"`  <br/> `filename:estimate`|Il primo esempio restituisce i file con la frase esatta "marketing plan" nel titolo. Il secondo esempio restituisce i file con la parola "estimate" nel nome file.|
|LastModifiedTime|La data dell'ultima modifica di un elemento.|`lastmodifiedtime>=05/01/2016`  <br/> `lastmodifiedtime>=05/10/2016 AND lastmodifiedtime<=06/1/2016`|Nel primo esempio vengono restituiti gli elementi modificati il 1° maggio 2016 o dopo il 1° maggio 2016. Nel secondo esempio vengono restituiti gli elementi modificati tra il 1° maggio 2016 e il 1 giugno 2016.|
|ModifiedBy|L'autore dell'ultima modifica di un elemento. Assicurati di usare il nome visualizzato dell'utente per questa proprietà.|`modifiedby:"Garth Fort"`|Tutti gli elementi in cui l’ultima modifica è stata apportata da Garth Fort.|
|Percorso|Percorso (URL) di un sito specifico in un SharePoint o OneDrive for Business sito.<br/><br/>Per restituire elementi solo dal sito specificato, è necessario aggiungere l'elemento finale alla `/` fine dell'URL, ad esempio `path: "https://contoso.sharepoint.com/sites/international/"` <br/><br/> Per restituire gli elementi che si trovano nelle cartelle del sito specificato nella proprietà path, è necessario aggiungere alla fine `/*` dell'URL, ad esempio  `path: "https://contoso.sharepoint.com/Shared Documents/*"`  <br/><br/> **Nota:** L'utilizzo della proprietà per OneDrive percorsi non restituirà file multimediali, ad esempio file .png, tiff o wav, nei risultati `Path` della ricerca. Utilizzare una proprietà del sito diversa nella query di ricerca per cercare file multimediali in OneDrive cartelle. <br/>|`path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/"`  <br/> `path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/*" AND filename:confidential`|Nel primo esempio vengono restituiti tutti gli elementi nel sito OneDrive for Business specificato. Nel secondo esempio vengono restituiti i documenti nel sito specificato (e nelle cartelle del sito) che contengono la parola "confidential" nel nome del file.|
|SharedWithUsersOWSUser|Documenti condivisi con l'utente specificato e visualizzati nella pagina Condivisi con **l'utente** corrente nel sito OneDrive for Business'utente. Si tratta di documenti che sono stati esplicitamente condivisi con l'utente specificato da altri utenti dell'organizzazione. Quando si esportano documenti che corrispondono a una query di ricerca che utilizza la proprietà SharedWithUsersOWSUser, i documenti vengono esportati dal percorso di contenuto originale della persona che ha condiviso il documento con l'utente specificato. Per ulteriori informazioni, vedere [Ricerca di contenuto del sito condiviso all'interno dell'organizzazione.](#searching-for-site-content-shared-within-your-organization)|`sharedwithusersowsuser:garthf`  <br/> `sharedwithusersowsuser:"garthf@contoso.com"`|Entrambi gli esempi restituiscono tutti i documenti interni che sono stati esplicitamente condivisi con Garth Fort e che vengono visualizzati nella pagina Condivisi con **me** nell'account OneDrive for Business Garth Fort.|
|Sito|L'URL di un sito o di un gruppo di siti nell'organizzazione.|`site:"https://contoso-my.sharepoint.com"`  <br/> `site:"https://contoso.sharepoint.com/sites/teams"`|Nel primo esempio vengono restituiti gli elementi OneDrive for Business siti per tutti gli utenti dell'organizzazione. Il secondo esempio restituisce gli elementi di tutti i siti dei team.|
|Dimensioni|Le dimensioni di un elemento, in byte.|`size>=1`  <br/> `size:1..10000`|Il primo esempio restituisce gli elementi di dimensioni maggiori di 1 byte. Il secondo esempio restituisce gli elementi di dimensioni comprese tra 1 e 10.000 byte.|
|Titolo|Il titolo del documento. La proprietà Title è metadati specificati nei Microsoft Office documenti. È diverso dal nome del file del documento.|`title:"communication plan"`|Qualsiasi documento contenente la frase "communication plan" nella proprietà di metadati Title di un documento di Office.|
|||||

## <a name="searchable-contact-properties"></a>Proprietà dei contatti disponibili per la ricerca

Nella tabella seguente sono elencate le proprietà dei contatti indicizzate e che è possibile cercare utilizzando gli strumenti di ricerca di eDiscovery. Si tratta delle proprietà che gli utenti possono configurare per i contatti (denominati anche contatti personali) che si trovano nella rubrica personale della cassetta postale di un utente. Per cercare i contatti, è possibile selezionare le cassette postali in cui eseguire la ricerca e quindi utilizzare una o più proprietà di contatto nella query con parole chiave.
  
> [!TIP]
> Per cercare valori contenenti spazi o caratteri speciali, utilizzare le virgolette doppie (" ") per contenere la frase. ad `businessaddress:"123 Main Street"` esempio.
  
|Proprietà |Descrizione proprietà |
|:-----|:-----|
|BusinessAddress|Indirizzo nella **proprietà Indirizzo** aziendale. La proprietà è anche denominata **indirizzo di** lavoro nella pagina delle proprietà del contatto.|
|BusinessPhone|Il numero di telefono in una delle proprietà **del Telefono** business.|
|CompanyName|Nome nella **proprietà Company.**|
|Reparto|Nome nella **proprietà Department.**|
|DisplayName|Nome visualizzato del contatto. Questo è il nome nella **proprietà Full Name** del contatto.|
|EmailAddress|L'indirizzo di qualsiasi proprietà dell'indirizzo di posta elettronica per il contatto. Gli utenti possono aggiungere più indirizzi di posta elettronica per un contatto. L'utilizzo di questa proprietà restituisce i contatti che corrispondono a uno qualsiasi degli indirizzi di posta elettronica del contatto.|
|FileAs|Proprietà **File as.** Questa proprietà viene utilizzata per specificare la modalità di elenco del contatto nell'elenco dei contatti dell'utente. Ad esempio, un contatto potrebbe essere elencato come  *FirstName,LastName*  *o LastName,FirstName*.|
|GivenName|Nome nella **proprietà First** Name.|
|HomeAddress|L'indirizzo in una delle **proprietà dell'indirizzo** principale.|
|HomePhone|Il numero di telefono in una delle proprietà **del numero** di telefono della casa.|
|IMAddress|La proprietà dell'indirizzo di messaggistica istantanea, che in genere è un indirizzo di posta elettronica utilizzato per la messaggistica istantanea.|
|MiddleName|Nome nella **proprietà Middle** name.|
|MobilePhone|Numero di telefono nella **proprietà Numero** di telefono cellulare.|
|Nickname|Nome nella **proprietà Nickname.**|
|OfficeLocation|Valore in **Office** o **Office posizione.**|
|OtherAddress|Valore della **proprietà Other** address.|
|Cognome|Nome nella **proprietà Last** name.|
|Titolo|Titolo nella proprietà **Titolo processo.**|
|||||

## <a name="searchable-sensitive-data-types"></a>Tipi di dati sensibili disponibili per la ricerca

È possibile utilizzare gli strumenti di ricerca di eDiscovery nel Centro conformità Microsoft 365 per cercare dati sensibili, ad esempio numeri di carta di credito o numeri di previdenza sociale, archiviati nei documenti nei siti SharePoint e OneDrive for Business. A tale scopo, è possibile utilizzare la proprietà e il nome (o ID) di un tipo `SensitiveType` di informazioni riservate in una query con parole chiave. Ad esempio, la query `SensitiveType:"Credit Card Number"` restituisce i documenti che contengono un numero di carta di credito. La query  `SensitiveType:"U.S. Social Security Number (SSN)"` restituisce i documenti che contengono un numero di previdenza sociale statunitense.

Per visualizzare un elenco dei tipi di informazioni riservate  che è possibile cercare, passare a Classificazioni dei dati Tipi di informazioni sensibili nel Centro Microsoft 365 \>  conformità. Oppure è possibile utilizzare il cmdlet **Get-DlpSensitiveInformationType** in PowerShell del Centro sicurezza & conformità per visualizzare un elenco di tipi di informazioni riservate.
  
Per ulteriori informazioni sulla creazione di query utilizzando la proprietà , vedere `SensitiveType` Form a query to find sensitive data stored on [sites](form-a-query-to-find-sensitive-data-stored-on-sites.md).

### <a name="limitations-for-searching-sensitive-data-types"></a>Limitazioni per la ricerca di tipi di dati sensibili

- Per cercare tipi di informazioni riservate personalizzati, è necessario specificare l'ID del tipo di informazioni riservate nella `SensitiveType` proprietà. L'utilizzo del nome di un tipo di informazioni riservate personalizzato (come illustrato nell'esempio per i tipi di informazioni riservate incorporati nella sezione precedente) non restituirà alcun risultato. Usa **la colonna Publisher** nella  pagina Tipi di informazioni riservate nel Centro conformità (o nella proprietà **Publisher** in PowerShell) per distinguere tra i tipi di informazioni riservate predefiniti e personalizzati. I tipi di dati sensibili incorporati hanno un valore `Microsoft Corporation` per la **proprietà Publisher.**

  Per visualizzare il nome e l'ID per i tipi di dati sensibili personalizzati nell'organizzazione, eseguire il comando seguente in PowerShell & Centro sicurezza e conformità:

  ```powershell
  Get-DlpSensitiveInformationType | Where-Object {$_.Publisher -ne "Microsoft Corporation"} | FT Name,Id
  ```

  È quindi possibile utilizzare l'ID nella proprietà di ricerca per restituire i documenti che contengono il tipo di dati sensibili `SensitiveType` personalizzato, ad esempio `SensitiveType:7e13277e-6b04-3b68-94ed-1aeb9d47de37`
  
- Non è possibile utilizzare i tipi di informazioni riservate e la proprietà di ricerca per cercare dati sensibili in locale nelle cassette postali Exchange Online `SensitiveType` riservate. Sono inclusi i messaggi di chat 1:1, i messaggi di chat di gruppo 1:N e le conversazioni del canale del team in Microsoft Teams perché tutto questo contenuto è archiviato nelle cassette postali. Tuttavia, è possibile utilizzare i criteri di prevenzione della perdita dei dati (DLP) per proteggere i dati di posta elettronica sensibili in transito. Per ulteriori informazioni, vedere [Informazioni sulla prevenzione della perdita di dati](dlp-learn-about-dlp.md) e Cercare e trovare dati [personali.](/compliance/regulatory/gdpr)
  
## <a name="search-operators"></a>Operatori di ricerca

Gli operatori di ricerca booleani, ad esempio **AND**, **OR** e **NOT,** consentono di definire ricerche più precise includendo o escludendo parole specifiche nella query di ricerca. Altre tecniche, ad esempio l'utilizzo di operatori di proprietà (ad esempio o ), virgolette, parentesi e caratteri jolly, consentono di perfezionare `>=` `..` una query di ricerca. Nella tabella seguente vengono elencati gli operatori che è possibile utilizzare per circoscrivere o ampliare i risultati della ricerca. 
  
|Operatore |Utilizzo |Descrizione |
|:-----|:-----|:-----|
|E|keyword1 AND keyword2|Restituisce gli elementi che includono tutte le parole chiave o le espressioni  `property:value` specificate. Ad esempio,  `from:"Ann Beebe" AND subject:northwind` verrebbero restituiti tutti i messaggi inviati da Ann Beebe che contenevano la parola northwind nella riga dell'oggetto. <sup>2</sup>|
|+|keyword1 + keyword2 + keyword3|Restituisce gli elementi che *contengono o* `keyword2` `keyword3` *e* che contengono anche `keyword1` .   Di conseguenza, questo esempio equivale alla query  `(keyword2 OR keyword3) AND keyword1` .  <br/> La `keyword1 + keyword2` query, con uno spazio dopo il **+** simbolo, non corrisponde all'utilizzo dell'operatore **AND.** Questa query equivale a restituire  `"keyword1 + keyword2"` gli elementi con la fase esatta  `"keyword1 + keyword2"` .|
|OPPURE|keyword1 OR keyword2|Restituisce gli elementi che includono una o più parole chiave o espressioni  `property:value` specificate. <sup>2</sup>|
|NOT|keyword1 NOT keyword2  <br/> NOT from:"Ann Beebe"  <br/> NOT kind:im|Esclude gli elementi specificati da una parola chiave o da  `property:value` un'espressione. Nel secondo esempio vengono esclusi i messaggi inviati da Ann Beebe. Nel terzo esempio vengono escluse eventuali conversazioni di messaggistica istantanea, ad esempio Skype for Business che vengono salvate nella cartella della cassetta postale Cronologia conversazioni. <sup>2</sup>|
|-|keyword1 -keyword2|Equivale all'operatore **NOT**. Questa query restituisce quindi gli elementi che contengono  `keyword1` ed escludono gli elementi che contengono  `keyword2` .|
|NEAR|keyword1 NEAR(n) keyword2|Restituisce gli elementi con parole che sono una accanto all'altra, dove n equivale al numero delle parole separate. Ad esempio, `best NEAR(5) worst` restituisce qualsiasi elemento in cui la parola "peggiore" si trova entro cinque parole di "migliore". Se non viene specificato alcun numero, la distanza predefinita è di otto parole. <sup>2</sup>|
|:|property:value|I due punti (:) nella sintassi specifica che il valore della proprietà da cercare  `property:value` contiene il valore specificato. Ad esempio,  `recipients:garthf@contoso.com` restituisce qualsiasi messaggio inviato a garthf@contoso.com.|
|=|property=value|Uguale all'operatore **:** .|
|\<|valore \< della proprietà|Indica che la proprietà da cercare è inferiore al valore specificato.  <sup>1</sup>|
|\>|valore \> della proprietà|Indica che la proprietà da cercare è maggiore del valore specificato. <sup>1</sup>|
|\<=|property \< =value|Indica che la proprietà da cercare è minore o uguale a un valore specifico. <sup>1</sup>|
|\>=|property \> =value|Indica che la proprietà da cercare è maggiore o uguale a un valore specifico. <sup>1</sup>|
|..|property:value1.. value2|Indica che la proprietà da cercare è maggiore o uguale a value1 e minore o uguale a value2. <sup>1</sup>|
|"  "|"fair value"  <br/> subject:"Quarterly Financials"|Utilizzare le virgolette doppie (" ") per cercare una frase o un termine esatto nelle parole chiave e nelle  `property:value` query di ricerca.|
|\*|cat\*  <br/> subject:set\*|La ricerca dei prefissi *(nota* anche come corrispondenza dei prefissi) consente di inserire un carattere jolly ( * ) alla fine di una parola in parole chiave o `property:value` query. Nelle ricerche con prefisso, la ricerca restituisce i risultati con termini che contengono la parola seguita da zero o più caratteri. Ad esempio, restituisce i documenti che contengono la parola `title:set*` "set", "setup" e "setting" (e altre parole che iniziano con "set") nel titolo del documento.  <br/><br/> **Nota:** È possibile utilizzare solo ricerche di prefissi. ad esempio, **cat _ o \* *_* set \* *_. Le ricerche suffisse (_* \* cat** ), le ricerche infissi (**c \* t**) e le ricerche sottostringhe (**\* cat \***) non sono supportate.<br/><br/>Inoltre, l'aggiunta di un punto ( \. ) in una ricerca con prefisso cambieranno i risultati restituiti. Questo perché un punto viene trattato come una parola di arresto. Ad esempio, la ricerca **di cat _ e la ricerca di \* *_* cat \* restituiranno** risultati diversi. È consigliabile non utilizzare un punto in una ricerca con prefisso. |
|(  )| (fair OR free) AND (from:contoso.com)  <br/>  (IPO OR initial) AND (stock OR shares)  <br/>  (quarterly financials)|Le parentesi raggruppano frasi, elementi e  `property:value` parole chiave booleani. Ad esempio,  `(quarterly financials)` restituisce gli elementi che contengono le parole trimestrali e finanziarie.|
|||||
   
> [!NOTE]
> <sup>1</sup> Utilizzare questo operatore per le proprietà con valori numerici o di data.<br/> <sup>2</sup> Gli operatori di ricerca booleani devono essere maiuscoli. ad **esempio, AND**. Se si utilizza un operatore minuscolo, ad esempio **e**, verrà considerato come una parola chiave nella query di ricerca. 
  
## <a name="search-conditions"></a>Condizioni di ricerca

È possibile aggiungere condizioni a una query di ricerca per restringere una ricerca e restituire un set di risultati più perfezionato. Ogni condizione aggiunge una clausola alla query di ricerca KQL creata ed eseguita all'avvio della ricerca.
  
[Condizioni per le proprietà comuni ](#conditions-for-common-properties)

[Condizioni per le proprietà della posta](#conditions-for-mail-properties)

[Condizioni per le proprietà dei documenti](#conditions-for-document-properties)

[Operatori utilizzati con condizioni](#operators-used-with-conditions)

[Linee guida per l'uso di condizioni](#guidelines-for-using-conditions)

[Esempi](#examples-of-using-conditions-in-search-queries)
  
### <a name="conditions-for-common-properties"></a>Condizioni per le proprietà comuni

Creare una condizione utilizzando le proprietà comuni quando si cercano cassette postali e siti nella stessa ricerca. Nella tabella seguente sono elencate le proprietà disponibili da utilizzare per l'aggiunta di una condizione.
  
| Condizione | Descrizione |
|:-----|:-----|
|Data|Per la posta elettronica, la data di un messaggio ricevuto da un destinatario o inviato da un mittente. Per i documenti, data dell'ultima modifica di un documento.|
|Mittente/Autore|Per la posta elettronica, l'utente che ha inviato un messaggio. Per i documenti, l'utente menzionato nel campo dell'autore dei documenti di Office. È possibile digitare più nomi, separati da virgole. Due o più valori sono collegati logicamente dall'operatore **OR**.|
|Dimensioni (in byte)|Per la posta elettronica e i documenti, la dimensione dell'elemento (in byte).|
|Oggetto/Titolo|Per la posta elettronica, il testo nella riga dell'oggetto di un messaggio. Per i documenti, il titolo del documento. Come spiegato in precedenza, la proprietà Title è un Microsoft Office documenti. È possibile digitare il nome di più di un oggetto/titolo, separati da virgole. Due o più valori sono collegati logicamente dall'operatore **OR**.|
|Etichetta di conservazione|Sia per la posta elettronica che per i documenti, le etichette di conservazione assegnate ai messaggi e ai documenti automaticamente dai criteri di etichetta automatica o dalle etichette di conservazione assegnate manualmente dagli utenti. Le etichette di conservazione vengono utilizzate per classificare la posta elettronica e i documenti per la governance delle informazioni e applicare le regole di conservazione in base alle impostazioni definite dall'etichetta. È possibile digitare parte del nome dell'etichetta di conservazione e utilizzare un carattere jolly oppure digitare il nome completo dell'etichetta. Per ulteriori informazioni sulle etichette di conservazione, vedere [Informazioni sui criteri di conservazione e sulle etichette di conservazione.](retention.md)|
|||
  
### <a name="conditions-for-mail-properties"></a>Condizioni per le proprietà della posta

Creare una condizione utilizzando le proprietà della posta quando si effettuano ricerche in cassette postali o cartelle pubbliche. Nella tabella seguente vengono elencate le proprietà della posta elettronica che è possibile utilizzare per una condizione. Queste proprietà sono un sottoinsieme delle proprietà di posta elettronica descritte in precedenza. Queste descrizioni vengono ripetute per comodità.
  
| Condizione | Descrizione |
|:-----|:-----|
|Tipo di messaggio| Il tipo di messaggio da cercare. Corrisponde alla proprietà della posta elettronica Kind (Tipo). Valori possibili:  <br/><br/>  contatti  <br/>  docs  <br/>  e-mail  <br/>  externaldata  <br/>  fax  <br/>  im  <br/>  journals  <br/>  riunioni  <br/>  microsoftteams  <br/>  note  <br/>  post  <br/>  rssfeeds  <br/>  attività  <br/>  segreteria telefonica|
|Partecipanti|Tutti i campi delle persone in un messaggio di posta elettronica. Questi campi sono From, To, Cc e Bcc.|
|Tipo|Proprietà della classe messaggio per un elemento di posta elettronica. Si tratta della stessa proprietà della proprietà di posta elettronica ItemClass. È anche una condizione multivalore. Per selezionare più classi messaggio, tenere premuto **CTRL** e quindi fare clic su due o più classi messaggio nell'elenco a discesa che si desidera aggiungere alla condizione. Ogni classe messaggio selezionata nell'elenco verrà collegata logicamente dall'operatore **OR** nella query di ricerca corrispondente.  <br/> Per un elenco delle classi messaggio (e dell'ID classe messaggio corrispondente) utilizzate da  Exchange e selezionabili nell'elenco Classe messaggio, vedere Tipi di elementi e classi [messaggio](/office/vba/outlook/Concepts/Forms/item-types-and-message-classes).|
|Ricevuto|La data in cui un messaggio di posta elettronica viene ricevuto da un destinatario. Corrisponde alla proprietà della posta elettronica Received (Ricevuto).|
|Destinatari|Tutti i campi dei destinatari in un messaggio di posta elettronica. Questi campi sono A, Cc e Ccn.|
|Mittente|Il mittente di un messaggio di posta elettronica.|
|Inviato|La data in cui un messaggio di posta elettronica viene inviato dal mittente. Corrisponde alla proprietà della posta elettronica Sent (Inviato).|
|Oggetto|Il testo nella riga dell'oggetto di un messaggio di posta elettronica.|
|A|Destinatario di un messaggio di posta elettronica nel campo A.|
|||
  
### <a name="conditions-for-document-properties"></a>Condizioni per le proprietà dei documenti

Creare una condizione utilizzando le proprietà del documento durante la ricerca di documenti SharePoint e OneDrive for Business siti. Nella tabella seguente vengono elencate le proprietà dei documenti che è possibile utilizzare per una condizione. Queste proprietà sono un sottoinsieme delle proprietà del sito descritte in precedenza. Queste descrizioni vengono ripetute per comodità.
  
| Condizione | Descrizione |
|:-----|:-----|
|Author|Il campo dell'autore dei documenti di Office, che persiste se un documento viene copiato. Ad esempio, se un utente crea un documento e lo invia tramite posta elettronica a un altro utente che lo carica SharePoint, il documento conserverà comunque l'autore originale.|
|Titolo|Il titolo del documento. La proprietà Title è rappresentata dai metadati specificati nei documenti di Office. È diverso dal nome del file del documento.|
|Creato|La data di creazione di un documento.|
|Data ultima modifica|La data dell'ultima modifica di un documento.|
|Tipo file|Estensione di un file. ad esempio docx, one, pptx o xlsx. Corrisponde alla proprietà dei siti FileExtension.|
|||
  
### <a name="operators-used-with-conditions"></a>Operatori utilizzati con condizioni

Quando si aggiunge una condizione, è possibile selezionare un operatore pertinente al tipo di proprietà per la condizione. Nella tabella seguente vengono descritti gli operatori utilizzati con condizioni e ne vengono elencati gli equivalenti utilizzati nella query di ricerca.
  
| Operatore | Equivalente nella query | Descrizione |
|:-----|:-----|:-----|
|Dopo|`property>date`|Utilizzato con condizioni relative alla data. Restituisce gli elementi che sono stati inviati, ricevuti o modificati dopo la data specificata. |
|Prima|`property<date`|Utilizzato con condizioni relative alla data. Restituisce gli elementi che sono stati inviati, ricevuti o modificati prima della data specificata.|
|Between|`date..date`|Utilizzato con condizioni relative alla data e alla dimensione. Se utilizzato con una condizione relativa alla data, restituisce gli elementi che sono stati inviati, ricevuti o modificati entro l'intervallo di date specificato. Se utilizzato con una condizione relativa alla dimensione, restituisce gli elementi di dimensioni comprese nell'intervallo specificato.|
|Contains any of|`(property:value) OR (property:value)`|Utilizzato con condizioni per le proprietà che specificano un valore di stringa. Restituisce gli elementi che contengono una parte qualsiasi di uno o più valori di stringa specificati.|
|Doesn't contain any of|`-property:value`  <br/> `NOT property:value`|Utilizzato con condizioni per le proprietà che specificano un valore di stringa. Restituisce gli elementi che non contengono parti del valore di stringa specificato.|
|Doesn't equal any of|`-property=value`  <br/> `NOT property=value`|Utilizzato con condizioni per le proprietà che specificano un valore di stringa. Restituisce gli elementi che non contengono la stringa specificata.|
|Uguale a|`size=value`|Restituisce elementi uguali alle dimensioni specificate. <sup>1</sup>|
|Equals any of|`(property=value) OR (property=value)`|Utilizzato con condizioni per le proprietà che specificano un valore di stringa. Restituisce gli elementi che corrispondono esattamente a uno o più valori di stringa specificati.|
|Maggiore|`size>value`|Restituisce gli elementi in cui la proprietà specificata è maggiore del valore specificato. <sup>1</sup>|
|Greater or equal|`size>=value`|Restituisce gli elementi in cui la proprietà specificata è maggiore o uguale al valore specificato. <sup>1</sup>|
|Meno|`size<value`|Restituisce elementi maggiori o uguali al valore specifico. <sup>1</sup>|
|Less or equal|`size<=value`|Restituisce elementi maggiori o uguali al valore specifico. <sup>1</sup>|
|Not equal|`size<>value`|Restituisce gli elementi che non sono uguali alle dimensioni specificate. <sup>1</sup>|
|||
   
> [!NOTE]
> <sup>1</sup> Questo operatore è disponibile solo per le condizioni che utilizzano la proprietà Size. 
  
### <a name="guidelines-for-using-conditions"></a>Linee guida per l'uso di condizioni

Tenere presente quanto segue quando si utilizzano le condizioni di ricerca.
  
- Una condizione è collegata logicamente alla query con parola chiave (specificata nella relativa casella) dall'operatore **AND**. Ciò significa che, per essere inclusi nei risultati, gli elementi devono soddisfare sia la query con parola chiave, sia la condizione. Ecco come le condizioni consentono di circoscrivere i risultati. 
    
- Se si aggiungono due o più condizioni a una query di ricerca (condizioni che specificano proprietà diverse), queste sono collegate logicamente dall'operatore **AND**. Ciò significa che vengono restituiti solo gli elementi che soddisfano tutte le condizioni (oltre alle query con parole chiave). 
    
- Se si aggiunge più di una condizione per la stessa proprietà, tali condizioni vengono collegate logicamente dall'operatore **OR**. Ciò significa che vengono restituiti gli elementi che soddisfano la query con parola chiave e una delle condizioni. Pertanto, i gruppi con le stesse condizioni vengono collegati tra loro dall'operatore **OR**, quindi gli insiemi di condizioni univoche vengono collegati dall'operatore **AND**. 
    
- Se si aggiungono più valori (separati da virgole o due punti) a una singola condizione, tali valori vengono collegati dall'operatore **OR**. Di conseguenza, vengono restituiti elementi se contengono uno qualsiasi dei valori specificati per la proprietà nella condizione. 
    
- La query di ricerca creata utilizzando la casella delle  parole chiave e le condizioni viene visualizzata nella pagina Ricerca, nel riquadro dei dettagli per la ricerca selezionata. In una query, tutto a destra della notazione indica le  `(c:c)` condizioni aggiunte alla query. 
    
- Le condizioni aggiungono solo le proprietà alla query di ricerca, non gli operatori. Per questo motivo la query visualizzata nel riquadro dei dettagli non mostra gli operatori a destra della  `(c:c)` notazione. KQL aggiunge gli operatori logici (in base alle regole illustrate in precedenza) quando viene eseguita la query. 
    
- È possibile utilizzare il controllo di trascinamento della selezione per rieseguire la sequenza dell'ordine delle condizioni. Fare clic sul controllo per una condizione e spostarlo verso l'alto o verso il basso.
    
- Come spiegato in precedenza, alcune proprietà della condizione consentono di digitare più valori (separati da punto e virgola). Ogni valore è connesso logicamente dall'operatore **OR** e restituisce la query `(filetype:docx) OR (filetype:pptx) OR (filetype:xlsx)` . Nella figura seguente viene illustrato un esempio di condizione con più valori.

    ![Una condizione con più valori](../media/SearchConditions1.png)
  
  > [!NOTE]
  > Non è possibile aggiungere più condizioni facendo clic **su Aggiungi condizione** per la stessa proprietà. È invece necessario fornire più valori per la condizione (separati da punti e virgola), come illustrato nell'esempio precedente.
  
### <a name="examples-of-using-conditions-in-search-queries"></a>Esempi

Negli esempi seguenti viene illustrata la versione basata su GUI di una query di ricerca con condizioni, la sintassi della query di ricerca visualizzata nel riquadro dei dettagli della ricerca selezionata (restituita anche dal cmdlet **Get-ComplianceSearch)** e la logica della query KQL corrispondente.
  
#### <a name="example-1"></a>Esempio 1

In questo esempio vengono restituiti SharePoint e OneDrive for Business che contengono un numero di carta di credito e sono stati modificati per l'ultima volta prima del 1° gennaio 2021.
  
 **GUI**
  
![Primo esempio relativo alle condizioni di ricerca](../media/SearchConditions2.png)
  
 **Sintassi della query di ricerca**
  
 `SensitiveType:"Credit Card Number"(c:c)(lastmodifiedtime<2021-01-01)`
  
 **Logica della query di ricerca**
  
 `SensitiveType:"Credit Card Number" AND (lastmodifiedtime<2021-01-01)`
  
Si noti nella schermata precedente che l'interfaccia utente di ricerca rafforza che la query con parole chiave e la condizione sono connesse dall'operatore **AND.**

#### <a name="example-2"></a>Esempio 2

In questo esempio vengono restituiti gli elementi di posta elettronica o i documenti che contengono la parola chiave "report", che sono stati inviati o creati prima del 1 aprile 2021 e che contengono la parola "northwind" nel campo oggetto dei messaggi di posta elettronica o nella proprietà title dei documenti. La query esclude le pagine Web che soddisfano gli altri criteri della ricerca.
  
 **GUI**
  
![Secondo esempio relativo alle condizioni di ricerca](../media/SearchConditions3.png)
  
 **Sintassi della query di ricerca**
  
 `report(c:c)(date<2021-04-01)(subjecttitle:"northwind")(-filetype:aspx)`
  
 **Logica della query di ricerca**
  
 `report AND (date<2021-04-01) AND (subjecttitle:"northwind") NOT (filetype:aspx)`
  
#### <a name="example-3"></a>Esempio 3

In questo esempio vengono restituiti i messaggi di posta elettronica o le riunioni del calendario inviate tra l'1/12/2019 e il 30/11/2020 e che contengono parole che iniziano con "phone" o "smartphone".
  
 **GUI**
  
![Terzo esempio relativo alle condizioni di ricerca](../media/SearchConditions4.png)
  
 **Sintassi della query di ricerca**
  
 `phone* OR smartphone*(c:c)(sent=2019-12-01..2020-11-30)(kind="email")(kind="meetings")`
  
 **Logica della query di ricerca**
  
 `phone* OR smartphone* AND (sent=2029-12-01..2020-11-30) AND ((kind="email") OR (kind="meetings"))`
  
## <a name="special-characters"></a>Caratteri speciali

Alcuni caratteri speciali non sono inclusi nell'indice di ricerca e pertanto non sono disponibili per la ricerca. Sono inclusi anche i caratteri speciali che rappresentano gli operatori di ricerca nella query di ricerca. Ecco un elenco di caratteri speciali che vengono sostituiti da uno spazio vuoto nella query di ricerca effettiva o che causano un errore di ricerca.

`+ - = : ! @ # % ^ & ; _ / ? ( ) [ ] { }`

## <a name="searching-for-site-content-shared-with-external-users"></a>Ricerca di contenuti dei siti condivisi con utenti esterni

È inoltre possibile utilizzare gli strumenti di ricerca eDiscovery nel Centro conformità per cercare i documenti archiviati nei siti SharePoint e OneDrive for Business condivisi con persone esterne all'organizzazione. Ciò consente di identificare informazioni proprietarie o sensibili condivise all'esterno dell'organizzazione. A tale scopo, è possibile utilizzare  `ViewableByExternalUsers` la proprietà in una query con parole chiave. Questa proprietà restituisce documenti o siti condivisi con utenti esterni utilizzando uno dei metodi di condivisione seguenti: 
  
- Invito alla condivisione che richiede agli utenti di accedere all'organizzazione come utente autenticato.

- Un collegamento guest anonimo, che consente a chiunque abbia questo collegamento di accedere alla risorsa senza dover essere autenticato.

Di seguito vengono descritti alcuni esempi:
  
- La query  `ViewableByExternalUsers:true AND SensitiveType:"Credit Card Number"` restituisce tutti gli elementi che sono stati condivisi con persone esterne all'organizzazione e contengono un numero di carta di credito.
  
- La query restituisce un elenco di documenti in tutti i siti del team dell'organizzazione che  `ViewableByExternalUsers:true AND ContentType:document AND site:"https://contoso.sharepoint.com/Sites/Teams"` sono stati condivisi con utenti esterni.

> [!TIP]
> Una query di ricerca, ad esempio, potrebbe restituire molti  `ViewableByExternalUsers:true AND ContentType:document` file aspx nei risultati della ricerca. Per eliminare questi (o altri tipi di file), è possibile utilizzare la proprietà per  `FileExtension` escludere tipi di file specifici, ad esempio  `ViewableByExternalUsers:true AND ContentType:document NOT FileExtension:aspx` .
  
Cosa viene considerato contenuto condiviso con persone esterne all'organizzazione? Documenti nei siti SharePoint e OneDrive for Business dell'organizzazione condivisi tramite l'invio di un invito alla condivisione o condivisi in posizioni pubbliche. Le attività utente seguenti, ad esempio, comportano contenuto visualizzabile dagli utenti esterni:
  
- Un utente condivide un file o una cartella con una persona esterna all'organizzazione.
  
- Un utente crea e invia un collegamento a un file condiviso a una persona esterna all'organizzazione. Questo collegamento consente all'utente esterno di visualizzare (o modificare) il file.
  
- Un utente invia un invito alla condivisione o un collegamento guest a una persona esterna all'organizzazione per visualizzare (o modificare) un file condiviso.
  
### <a name="issues-using-the-viewablebyexternalusers-property"></a>Problemi relativi all'utilizzo della proprietà ViewableByExternalUsers

Sebbene la proprietà rappresenti lo stato di condivisione di un documento o di un sito con utenti esterni, esistono alcune avvertenze sull'operazione che questa proprietà esegue e  `ViewableByExternalUsers` non riflette. Negli scenari seguenti il valore della proprietà non verrà aggiornato e i risultati di una query di ricerca che utilizza questa proprietà potrebbero non essere  `ViewableByExternalUsers` accurati. 
  
- Modifiche ai criteri di condivisione, ad esempio la disattivazione della condivisione esterna per un sito o per l'organizzazione. La proprietà continuerà a mostrare i documenti condivisi in precedenza come accessibili esternamente anche se l'accesso esterno potrebbe essere stato revocato.
    
- Modifiche apportate all'appartenenza ai gruppi, ad esempio l'aggiunta o la rimozione di utenti esterni Microsoft 365 gruppi o Microsoft 365 di sicurezza. La proprietà non verrà aggiornata automaticamente per gli elementi a cui il gruppo ha accesso.
    
- Invio di inviti alla condivisione a utenti esterni in cui il destinatario non ha accettato l'invito e pertanto non ha ancora accesso al contenuto.
    
In questi scenari, la proprietà non rifletterà lo stato di condivisione corrente fino a quando il sito o la raccolta documenti non viene nuovamente ricercata e  `ViewableByExternalUsers` reindicizzazione. 

## <a name="searching-for-site-content-shared-within-your-organization"></a>Ricerca del contenuto del sito condiviso all'interno dell'organizzazione

Come spiegato in precedenza, è possibile utilizzare la proprietà in modo da cercare i documenti condivisi tra gli utenti  `SharedWithUsersOWSUser` dell'organizzazione. Quando una persona condivide un file (o una cartella) con un altro utente all'interno dell'organizzazione, nella pagina Condivisi con **me** viene visualizzato un collegamento al file condiviso nell'account OneDrive for Business della persona con cui è stato condiviso il file. Ad esempio, per cercare i documenti che sono stati condivisi con Sara Davis, è possibile utilizzare la query  `SharedWithUsersOWSUser:"sarad@contoso.com"` . Se si esportano i risultati di questa ricerca, verranno scaricati i documenti originali (che si trovano nel percorso del contenuto della persona che ha condiviso i documenti con Sara).
  
I documenti devono essere condivisi in modo esplicito con un utente specifico per essere restituiti nei risultati della ricerca quando si utilizza la  `SharedWithUsersOWSUser` proprietà . Ad esempio, quando una persona condivide un documento nel proprio account OneDrive, ha la possibilità di condividerlo con chiunque (all'interno o all'esterno dell'organizzazione), condividerlo solo con persone all'interno dell'organizzazione o condividerlo con una persona specifica. Ecco uno screenshot della **finestra** Condividi in OneDrive, che mostra le tre opzioni di condivisione. 
  
![Solo i file condivisi con persone specifiche verranno restituiti da una query di ricerca che utilizza la proprietà SharedWithUsersOWSUser](../media/469a4b61-68bd-4ab0-b612-ab6302973886.png)
  
Solo i documenti condivisi utilizzando la terza opzione (condivisa con persone **specifiche)** verranno restituiti da una query di ricerca che utilizza la  `SharedWithUsersOWSUser` proprietà. 

## <a name="searching-for-skype-for-business-conversations"></a>Ricerca di Skype for Business conversazioni

È possibile utilizzare la query con parole chiave seguente per cercare in modo specifico il contenuto nelle Skype for Business conversazioni:

```powershell
kind:im
```

La query di ricerca precedente restituisce anche chat da Microsoft Teams. Per evitare questo problema, è possibile limitare i risultati della ricerca in modo da includere solo Skype for Business conversazioni utilizzando la query con parole chiave seguente:

```powershell
kind:im AND subject:conversation
```

La query con parole chiave precedente esclude le chat in Microsoft Teams perché le conversazioni Skype for Business vengono salvate come messaggi di posta elettronica con una riga Subject che inizia con la parola "Conversation".

Per cercare Skype for Business conversazioni che si sono verificate in un intervallo di date specifico, utilizzare la query con parole chiave seguente:

```powershell
kind:im AND subject:conversation AND (received=startdate..enddate)
```

## <a name="character-limits-for-searches"></a>Limiti di caratteri per le ricerche

Esiste un limite di 4.000 caratteri per le query di ricerca durante la ricerca di contenuto in SharePoint siti e OneDrive account.  
Ecco come viene calcolato il numero totale di caratteri nella query di ricerca:

- I caratteri nella query di ricerca con parole chiave (inclusi i campi utente e di filtro) vengono conteggiati in base a questo limite.

- I caratteri in qualsiasi proprietà location (ad esempio gli URL di tutti i siti SharePoint o le posizioni OneDrive ricercate) vengono conteggiati rispetto a questo limite.

- I caratteri in tutti i filtri delle autorizzazioni di ricerca applicati all'utente che esegue il conteggio della ricerca rispetto al limite.

Per ulteriori informazioni sui limiti dei caratteri, vedere [Limiti di ricerca eDiscovery](limits-for-content-search.md#search-limits).

> [!NOTE]
> Il limite di 4.000 caratteri si applica a Ricerca contenuto, Core eDiscovery e Advanced eDiscovery.

## <a name="search-tips-and-tricks"></a>Suggerimenti pratici per la ricerca

- Per le ricerche con parole chiave non viene eseguita la distinzione tra maiuscole e minuscole. Ad esempio, **cat** e **CAT** restituiscono gli stessi risultati.

- Gli operatori **booleani AND**, **OR**, **NOT** e **NEAR** devono essere maiuscoli. 

- Uno spazio tra due parole chiave o due  `property:value` espressioni corrisponde all'utilizzo di **AND**. Ad esempio,  `from:"Sara Davis" subject:reorganization` restituisce tutti i messaggi inviati da Sara Davis che contengono la parola riorganizzazione nella riga dell'oggetto. 

- Utilizzare una sintassi corrispondente al `property:value` formato. I valori non fanno distinzione tra maiuscole e minuscole e non possono avere uno spazio dopo l'operatore. Se è presente uno spazio, il valore desiderato sarà una ricerca full-text. Ad esempio, cerca "pilarp" come parola chiave, anziché per i messaggi inviati `to: pilarp` a pilarp. 

- Quando si cerca una proprietà relativa al destinatario, come To (A), From (Da), Cc (Cc) o Recipients (Destinatari), è possibile utilizzare un indirizzo SMTP, un alias o un nome visualizzato per denotare un destinatario. Ad esempio, è possibile utilizzare pilarp@contoso.com, pilarp o "Pilar Pinilla".

- È possibile utilizzare solo ricerche di prefissi. ad esempio, **cat _ o \* *_* set \* *_. Le ricerche suffisse (_* \* cat**), le ricerche infissi (**c \* t**) e le ricerche sottostringhe (**\* cat \***) non sono supportate.

- Quando si esegue una ricerca in una proprietà, utilizzare le virgolette doppie (" ") se il valore di ricerca è costituito da più parole. Ad esempio, restituisce i messaggi che contengono budget nella riga dell'oggetto e che contengono Q1 in qualsiasi punto del messaggio `subject:budget Q1` o in una delle proprietà del messaggio.   Using `subject:"budget Q1"` restituisce tutti i messaggi che contengono il budget **Q1** in qualsiasi punto della riga dell'oggetto.

- Per escludere i contenuti contrassegnati con un determinato valore della proprietà dai risultati della ricerca, inserire un segno meno (-) prima del nome della proprietà. Ad esempio, `-from:"Sara Davis"` esclude tutti i messaggi inviati da Sara Davis.

- È possibile esportare gli elementi in base al tipo di messaggio. Ad esempio, per esportare Skype conversazioni e chat in Microsoft Teams, utilizzare la sintassi `kind:im` . Per restituire solo i messaggi di posta elettronica, utilizzare `kind:email` . Per restituire chat, riunioni e chiamate in Microsoft Teams, utilizzare `kind:microsoftteams` .

- Come spiegato in precedenza, durante la ricerca nei siti è necessario aggiungere il finale alla fine dell'URL quando si utilizza la proprietà per restituire solo gli elementi `/` `path` in un sito specificato. Se non si include l'elemento finale, verranno restituiti anche gli elementi di un sito con un nome di percorso `/` simile. Ad esempio, se si utilizzano `path:sites/HelloWorld` gli elementi dei siti denominati o che `sites/HelloWorld_East` `sites/HelloWorld_West` verrebbero restituiti. Per restituire elementi solo dal sito HelloWorld, è necessario utilizzare `path:sites/HelloWorld/` .
