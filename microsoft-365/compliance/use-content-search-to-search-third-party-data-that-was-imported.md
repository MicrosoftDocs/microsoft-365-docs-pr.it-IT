---
title: Utilizzare Ricerca contenuto per cercare dati importati di terze parti
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: Utilizzare lo strumento Ricerca contenuto di eDiscovery per cercare gli elementi importati nelle cassette postali di Microsoft 365 da un'origine dati di terze parti creando query.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 24ca63cf78b85f7b8b5181d5babd16058b641128
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324572"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a>Utilizzare Ricerca contenuto per cercare dati di terze parti importati da un connettore partner personalizzato

È possibile utilizzare lo strumento Ricerca contenuto [eDiscovery](content-search.md) nel Centro sicurezza & conformità per cercare gli elementi importati nelle cassette postali di Microsoft 365 da un'origine dati di terze parti. È possibile creare una query per eseguire ricerche in tutti gli elementi di dati di terze parti importati oppure creare una query per cercare elementi di dati di terze parti specifici. È inoltre possibile creare un criterio di conservazione basato su query o un blocco eDiscovery basato su query per conservare i dati di terze parti.
  
Per ulteriori informazioni sull'utilizzo di un partner per importare dati di terze parti e un elenco dei tipi di dati di terze parti che è possibile importare in Microsoft 365, vedere Collaborare con un partner per archiviare dati di terze parti [in Office 365.](work-with-partner-to-archive-third-party-data.md)

> [!IMPORTANT]
> Le indicazioni fornite in questo articolo si applicano solo ai dati di terze parti importati da un connettore partner personalizzato. Questo articolo non si applica ai dati di terze [](archiving-third-party-data.md#third-party-data-connectors) parti importati tramite i connettori di dati di terze parti nel Centro conformità Microsoft.
  
## <a name="creating-a-query-to-search-all-third-party-data"></a>Creazione di una query per la ricerca di tutti i dati di terze parti

Per cercare (o mettere in attesa) qualsiasi tipo di dati di terze parti importati in Office 365, è possibile usare la coppia proprietà-valore del messaggio nella casella delle parole chiave per una ricerca di contenuto o durante la creazione di un'esenzione basata su  `kind:externaldata` query. Ad esempio, per cercare gli elementi importati da qualsiasi origine dati di terze parti e contenere la parola "contoso" nella proprietà Subject dell'elemento importato, è necessario utilizzare la query seguente: 
  
```powershell
kind:externaldata AND subject:contoso
```

L'esempio di query con parole chiave precedente include la proprietà subject. Per un elenco di altre proprietà per gli elementi di dati di terze parti che possono essere incluse in una query con parole chiave, vedere la sezione "Ulteriori informazioni" in Collaborare con un partner per archiviare dati di terze parti [in Office 365.](work-with-partner-to-archive-third-party-data.md#more-information)
  
Quando si creano query per cercare e contenere dati di terze parti, è inoltre possibile utilizzare le condizioni per restringere i risultati della ricerca. Per ulteriori informazioni sulla creazione di query di Ricerca contenuto, vedere [Query con parole chiave e condizioni di ricerca per Ricerca contenuto.](keyword-queries-and-search-conditions.md)
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a>Creazione di una query per la ricerca di tipi specifici di dati di terze parti

Anziché cercare tutti i tipi di dati di terze parti, è possibile creare query che cercano solo un tipo specifico di dati di terze parti utilizzando la seguente proprietà del *messaggio:* coppia di valori nella casella delle parole chiave per una ricerca di contenuto:
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

Ad esempio, per cercare i dati di Facebook che contengono la parola "contoso" nella proprietà Subject, è necessario utilizzare la query seguente:
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

Nella tabella seguente sono elencati i tipi di dati di terze parti che è possibile cercare e il valore da utilizzare per la proprietà del messaggio per cercare in modo specifico tale tipo di  `itemclass:` dati di terze parti. La sintassi della query non fa distinzione tra maiuscole e minuscole. 
  
|**Tipo di dati di terze parti**|**Valore della  `itemclass:` proprietà**|
|:-----|:-----|
|AIM  <br/> | `ipm.externaldata.AIM*` <br/> |
|American Idol  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|AOL con Pivot Client   <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|Apple Juice  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|Ares  <br/> | `ipm.externaldata.Ares*` <br/> |
|Axs Encrypted  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|Axs Exchange  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|Axs Local Archive  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|Segnaposto per assi  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|Axs Signed  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|Bazaarvoice  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|Bearshare  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|BitTorrent  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|Blackberry  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|Registri chiamate BlackBerry  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|BlackBerry Messenger  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|BlackBerry PIN  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|BlackBerry SMS  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|Bloomberg  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|Bloomberg Message  <br/> | `ipm.externaldata.conversation.Bloomberg Message*` <br/> |
|Messaggistica Bloomberg  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|Box  <br/> | `ipm.externaldata.Box*` <br/> |
|Server presenza messaggistica istantanea Cisco &amp;  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|Cisco Jabber  <br/> | `ipm.externaldata.Jabber*` <br/> |
|CipherCloud per Salesforce Chatter  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|Connessione diretta  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|Facebook  <br/> | `ipm.externaldata.Facebook*` <br/> |
|FastTrack  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|FXConnect  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|Flickr  <br/> | `ipm.externaldata.Flickr*` <br/> |
|Gnutella  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|Google+  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|Google Talk  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|GoToMyPC  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|HipChat  <br/> | `ipm.externaldata.HipChat*` <br/> |
|Hopster  <br/> | `ipm.externaldata.Hopster*` <br/> |
|HubConnex  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|IBM Connections  <br/> | `ipm.externaldata.Connections*` <br/> |
|IBM SameTime  <br/> | `ipm.externaldata.Sametime*` <br/> |
|ICE Chat  <br/> | `ipm.externaldata.conversation.Ice Chat*` <br/> |
|Indii Messenger  <br/> | `ipm.externaldata.Indii*` <br/> |
|Instagram  <br/> | `ipm.externaldata.Instagram*` <br/> |
|Instant Bloomberg  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|InvestEdge  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|IRC  <br/> | `ipm.externaldata.IRC*` <br/> |
|Jive  <br/> | `ipm.externaldata.Jive*` <br/> |
|JiveApiRetention  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|JXTA  <br/> | `ipm.externaldata.JXTA*` <br/> |
|LinkedIn  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|MFTP  <br/> | `ipm.externaldata.MFTP*` <br/> |
|Microsoft UC  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|Allineamento della mente  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|Mobile Guard  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|MSN  <br/> | `ipm.externaldata.MSN*` <br/> |
|MySpace  <br/> | `ipm.externaldata.MySpace*` <br/> |
|NEONetwork  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|OpenNap  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|Pinterest  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|Pivot  <br/> | `ipm.externaldata.Pivot*` <br/> |
|QQ  <br/> | `ipm.externaldata.QQ*` <br/> |
|Microsoft SharePoint  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|Salesforce Chatter  <br/> | `ipm.externaldata.Chatter*` <br/> |
|Skype for Business  <br/> | `ipm.externaldata.Skype*` <br/> |
|Slack Enterprise Grid  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|SoftEther  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|Squawker  <br/> | `ipm.externaldata.Squawker*` <br/> |
|Symphony  <br/> | `ipm.externaldata.Symphony*` <br/> |
|Thomson Reuters  <br/> | `ipm.externaldata.Reuters*` <br/> |
| Thomson Reuters Eikon Messenger  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|Tor  <br/> | `ipm.externaldata.Tor*` <br/> |
|TTT  <br/> | `ipm.externaldata.TTT*` <br/> |
|Twitter  <br/> | `ipm.externaldata.Twitter*` <br/> |
|Chat UBS  <br/> | `ipm.externaldata.UBS*` <br/> |
|Vimeo  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|WinMX  <br/> | `ipm.externaldata.WinMX*` <br/> |
|Winny  <br/> | `ipm.externaldata.Winny*` <br/> |
|Yahoo!  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|Yammer  <br/> | `ipm.externaldata.Yammer*` <br/> |
|YellowJacket  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|YouTube  <br/> | `ipm.externaldata.YouTube*` <br/> |
