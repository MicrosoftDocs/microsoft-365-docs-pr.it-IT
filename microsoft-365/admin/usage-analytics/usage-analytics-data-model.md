---
title: Modello di dati nell'analisi dell'utilizzo di Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 08c5307c-4a6b-4761-8410-a6c96725760f
description: "Informazioni su come l'analisi dell'utilizzo si connette a un'API e fornisce un andamento mensile dell'utilizzo di vari servizi di Microsoft 365.  "
ms.openlocfilehash: d2d08a46ad6bcf3659c78a381ce20d99ea805ac7
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42253544"
---
# <a name="microsoft-365-usage-analytics-data-model"></a>Modello di dati nell'analisi dell'utilizzo di Microsoft 365

## <a name="data-for-the-microsoft-365-usage-analytics-tables"></a>Dati per le tabelle di analisi di utilizzo di Microsoft 365

L'analisi di utilizzo di Microsoft 365 si connette a un'API che espone un modello di dati multidimensionali. Le API sono in anteprima e sono accessibili al `https://reports.office.com/pbi/v1.0/\<tenantid\>` (sostituire \<idtenant\> con il GUID del tenant). 
  
> [!NOTE]
> Per ulteriori informazioni, vedere [Working with microsoft 365 usage reports in Microsoft Graph](https://go.microsoft.com/fwlink/p/?linkid=864336). 
  
Questa API fornisce informazioni sull'andamento mensile dell'utilizzo dei vari servizi di Microsoft 365. Per i dati esatti restituiti dall'API fare riferimento alla tabella contenuta nella sezione seguente.
  
## <a name="data-tables-returned-by-the-microsoft-365-reporting-api"></a>Tabelle di dati restituite dall'API dei report di Microsoft 365

|**Nome di tabella**|**Informazioni nella tabella**|**Intervallo di date**|
|:-----|:-----|:-----|
|Tenant Product Usage  <br/> |Contiene i totali mensili degli utenti abilitati, degli utenti attivi, degli utenti mantenuti mese dopo mese, dei nuovi utenti e il numero di cumulativo di tutti gli utenti attivi.  <br/> |Contiene i dati aggregati mensili per un periodo di distribuzione di 12 mesi incluso il mese parziale corrente.  <br/> |
|Tenant Product Activity  <br/> |Contiene i totali mensili delle attività e il numero di utenti attivi per varie attività all'interno dei prodotti.  <br/> Vedere la [definizione di utente attivo](active-user-in-usage-reports.md) per informazioni sulle attività all'interno di un prodotto che vengono restituite in questa tabella dati.  <br/> |Contiene i dati aggregati mensili per un periodo di distribuzione di 12 mesi incluso il mese parziale corrente.  <br/> |
|Tenant Office Licenses  <br/> |Contiene i dati sul numero di abbonamenti a Microsoft Office assegnati agli utenti  <br/> |Contiene i dati sullo stato di fine mese per un periodo di distribuzione di 12 mesi incluso il mese parziale corrente.  <br/> |
|Tenant Mailbox Usage  <br/> |Contiene i dati relativi alla cassetta postale dell'utente, come il conteggio totale della cassetta postale e l'uso dello spazio di archiviazione.  <br/> |Contiene i dati sullo stato di fine mese per un periodo di distribuzione di 12 mesi incluso il mese parziale corrente.  <br/> |
|Tenant Client Usage  <br/> |Contiene i dati relativi al numero di utenti che usano attivamente client/dispositivi specifici per connettersi a Exchange Online, Skype for Business e Yammer.  <br/> |Contiene i dati aggregati mensili per un periodo di distribuzione di 12 mesi incluso il mese parziale corrente.  <br/> |
|Tenant SharePoint Online Usage  <br/> |Contiene i dati relativi ai siti di SharePoint, inclusi i siti del gruppo o del team, ad esempio il numero totale dei siti, il numero di documenti del sito, il numero di file per tipo di attività e lo spazio di archiviazione usato.  <br/> |Contiene i dati sullo stato di fine mese per un periodo di distribuzione di 12 mesi incluso il mese parziale corrente.  <br/> |
|Tenant OneDrive for Business Usage  <br/> |Contiene i dati relativi gli account di OneDrive, ad esempio il numero di account, il numero di documenti nelle varie istanze di OneDrive, lo spazio di archiviazione usato e il numero di file per tipo di attività.  <br/> |Contiene i dati sullo stato di fine mese per un periodo di distribuzione di 12 mesi incluso il mese parziale corrente.  <br/> |
|Utilizzo di gruppi di Microsoft 365 tenant  <br/> |Contiene i dati relativi all'utilizzo dei gruppi di Microsoft 365, tra cui Mailbox, SharePoint e Yammer.  <br/> |Contiene i dati sullo stato di fine mese per un periodo di distribuzione di 12 mesi incluso il mese parziale corrente.  <br/> |
|Tenant Office Activation  <br/> |Contiene i dati sul numero di attivazioni dell'abbonamento a Office, sul numero di attivazioni per ogni dispositivo (Android/iOS/Mac/PC), le attivazioni per piano di servizio, ad esempio Office Proplus, Visio, Project.  <br/> |Contiene i dati sullo stato di fine mese per un periodo di distribuzione di 12 mesi incluso il mese parziale corrente.  <br/> |
|User State  <br/> |Contiene metadati sugli utenti, tra cui il nome visualizzato dell'utente, i prodotti assegnati, la posizione, il reparto, il titolo e la società. Questi dati sono relativi agli utenti a cui sono state assegnate licenze nel corso dell'ultimo mese completo. Ogni utente è rappresentato in modo univoco da un ID utente.  <br/> |Questi dati sono relativi agli utenti a cui è stata assegnata una licenza nel corso dell'ultimo mese completo.  <br/> |
|User Activity  <br/> |Contiene informazioni sulle attività eseguite dagli utenti con licenza.  <br/> Vedere la [definizione di utente attivo](active-user-in-usage-reports.md) per informazioni sulle attività all'interno di un prodotto che vengono restituite in questa tabella dati.  <br/> |Questi dati sono relativi agli utenti che hanno eseguito un'attività in uno dei servizi nel corso dell'ultimo mese completo.  <br/> |
   
Espandere le sezioni seguenti per visualizzare le informazioni dettagliate per ogni tabella di dati.
  
### <a name="data-table---user-state"></a>Tabella di dati - User State

Questa tabella contiene i dettagli a livello di utente per tutti gli utenti a cui è stata assegnata una licenza durante l'ultimo mese completo. I dati vengono importati da Azure Active Directory.
  
|**Nome colonna**|**Descrizione della colonna**|
|:-----|:-----|
|UserId  <br/> |ID utente univoco che rappresenta un utente e consente di unire altre tabelle di dati all'interno del set di dati.  <br/> |
|Timeframe  <br/> |Valore del mese per cui questa tabella contiene dati.  <br/> |
|UPN  <br/> |Nome dell'entità utente, che identifica in modo univoco l'utente per poter partecipare con altre origini dati esterne.  <br/> |
|DisplayName  <br/> |Nome visualizzato dell'utente.  <br/> |
|IDType  <br/> |Il tipo di ID è impostato su 1 se l'utente è un utente di Yammer che si connette utilizzando il proprio ID Yammer o 0 se si connette a Yammer utilizzando il relativo ID Microsoft 365.  <br/> Il valore è 1 per rappresentare gli utenti che si connettono a Yammer con il relativo ID Yammer e non con il relativo ID Microsoft 365  <br/> |
|HasLicenseEXO  <br/> |Impostato su True se all'utente è assegnata una licenza che gli consente di usare Exchange.  <br/> |
|HasLicenseODB  <br/> |Impostato su True se all'utente è assegnata una licenza che gli consente di usare OneDrive for Business.  <br/> |
|HasLicenseSPO  <br/> |Impostato su True se all'utente è assegnata una licenza che gli consente di usare SharePoint Online.  <br/> |
|HasLicenseYAM  <br/> |Impostato su True se all'utente è assegnata una licenza che gli consente di usare Yammer.  <br/> |
|HasLicenseSFB  <br/> |Impostato su True se all'utente è assegnata una licenza che gli consente di usare Skype for Business.  <br/> |
|HasLicenseTeams  <br/> |Impostare su true se all'utente è stata assegnata una licenza e abilitare l'utilizzo di Microsoft teams.  <br/> |
|Company  <br/> |Dati aziendali rappresentati in Azure Active Directory per questo utente.  <br/> |
|Reparto  <br/> |Dati del reparto rappresentati in Azure Active Directory per questo utente.  <br/> |
|LocationCity  <br/> |Dati della città rappresentati in Azure Active Directory per questo utente.  <br/> |
|LocationCountry  <br/> |Dati del paese rappresentati in Azure Active Directory per questo utente.  <br/> |
|LocationState  <br/> |Dati dello stato rappresentati in Azure Active Directory per questo utente.  <br/> |
|LocationOffice  <br/> |Ufficio dell'utente.  <br/> |
|Title  <br/> |Dati del titolo rappresentati in Azure Active Directory per questo utente.  <br/> |
|Eliminato  <br/> |Ha valore true se l'utente è stato eliminato da Microsoft 365 nell'ultimo mese completo.  <br/> |
|DeletedDate  <br/> |Data in cui l'utente è stato eliminato da Microsoft 365.  <br/> |
|YAM_State  <br/> |Stati dell'utente nel sistema Yammer, ossia attivo, eliminato o sospeso.  <br/> |
|YAM_ActivationDate  <br/> |Data in cui l'utente è entrato nello stato attivo in Yammer.  <br/> |
|YAM_DeletionDate  <br/> |Data in cui l'utente è entrato nello stato eliminato in Yammer.  <br/> |
|YAM_SuspensionDate  <br/> |Data in cui l'utente è entrato nello stato sospeso in Yammer.  <br/> |
   
### <a name="data-table---user-activity"></a>Tabella di dati - User Activity

Questa tabella contiene i dati relativi a ogni utente che ha eseguito un'attività in uno dei servizi nel mese scorso.
  
|**Nome colonna**|**Descrizione della colonna**|
|:-----|:-----|
|UserID  <br/> |ID utente univoco che rappresenta un utente e consente di unire altre tabelle di dati all'interno del set di dati.  <br/> |
|IDType  <br/> |Il tipo di ID è impostato su 1 se l'utente è un utente di Yammer che si connette utilizzando il proprio ID Yammer o 0 se si connette a Yammer utilizzando il relativo ID Microsoft 365.  <br/> Il valore è 1 per rappresentare gli utenti che si connettono a Yammer con il relativo ID Yammer e non con il relativo ID Microsoft 365  <br/> |
|Timeframe  <br/> |Valore del mese per cui questa tabella rappresenta dati.  <br/> |
|EXO_EmailSent  <br/> |Numero di messaggi di posta elettronica inviati.  <br/> |
|EXO_EmailReceived  <br/> |Numero di messaggi di posta elettronica ricevuti.  <br/> |
|EXO_EmailRead  <br/> |Numero di attività di lettura di messaggi di posta elettronica eseguite dall'utente. Può essere la lettura ripetuta di un messaggio già letto o un messaggio ricevuto in precedenza.  <br/> |
|EXO_AppointmentCreated  <br/> |Numero di appuntamenti creati.  <br/> |
|EXO_MeetingAccepted  <br/> |Numero di riunioni accettate.  <br/> |
|EXO_MeetingCancelled  <br/> |Numero di riunioni annullate.  <br/> |
|EXO_MeetingDeclined  <br/> |Numero di riunioni rifiutate.  <br/> |
|EXO_MeetingSent  <br/> |Numero di riunioni inviate.  <br/> |
|ODB_FileViewedModified  <br/> |Numero di file con cui l'utente ha interagito in OneDrive for Business, ad esempio file creati, aggiornati, eliminati, visualizzati o scaricati.  <br/> |
|ODB_FileSynched  <br/> |Numero di file che l'utente ha sincronizzato in OneDrive for Business.  <br/> |
|ODB_FileSharedInternally  <br/> |Numero di file che l'utente ha condiviso internamente da qualsiasi OneDrive for business o con utenti all'interno di gruppi (che potrebbero includere utenti esterni).  <br/> |
|ODB_FileSharedExternally  <br/> |Numero di file che l'utente ha condiviso esternamente da OneDrive for Business.  <br/> |
|ODB_AccessByOwner  <br/> |Numero di file con cui l'utente ha interagito e che si trovano nel suo OneDrive for Business.  <br/> |
|ODB_AccessOthers  <br/> |Numero di file con cui l'utente ha interagito e che si trovano in OneDrive for Business di un altro utente.  <br/> |
|SPO_GroupFileViewedModified  <br/> |Numero di file con cui l'utente ha interagito in un sito del gruppo.  <br/> |
|SPO_GroupFileSynched  <br/> |Numero di file che l'utente ha sincronizzato in un sito del gruppo.  <br/> |
|SPO_GroupFileSharedInternally  <br/> |Il numero di file che sono stati condivisi con gli utenti all'interno dell'organizzazione o con utenti all'interno di gruppi (che possono includere utenti esterni).  <br/> |
|SPO_GroupFileSharedExternally  <br/> |Numero di file che l'utente ha condiviso esternamente da un sito del gruppo.  <br/> |
|SPO_GroupAccessByOwner  <br/> |Numero di file con cui l'utente ha interagito e che si trovano in un sito del gruppo di cui è proprietario.  <br/> |
|SPO_GroupAccessByOthers  <br/> |Numero di file con cui l'utente ha interagito e che si trovano in un sito del gruppo di cui è proprietario un altro utente.  <br/> |
|SPO_OtherFileViewedModified  <br/> |Il numero di file con cui l'utente ha interagito in qualsiasi altro sito.  <br/> |
|SPO_OtherFileSynched  <br/> |Numero di file che l'utente ha sincronizzato da qualsiasi altro sito.  <br/> |
|SPO_OtherFileSharedInternally  <br/> |Numero di file che l'utente ha condiviso internamente da qualsiasi altro sito o con utenti all'interno di gruppi (che potrebbero includere utenti esterni). <br/> |
|SPO_OtherFileSharedExternally  <br/> |Numero di file che l'utente ha condiviso esternamente da qualsiasi altro sito.  <br/> |
|SPO_OtherAccessedByOwner  <br/> |Il numero di siti con cui l'utente ha interagito e che si trovano in un altro sito di loro proprietà.  <br/> |
|SPO_OtherAccessedByOthers  <br/> |Il numero di siti con cui l'utente ha interagito e che si trovano in un altro sito proprietario di un altro utente.  <br/> |
|SPO_TeamFileViewedModified  <br/> |Numero di file con cui l'utente ha interagito in un sito del team.  <br/> |
|SPO_TeamFileSynched  <br/> |Numero di file che l'utente ha sincronizzato in un sito del team.  <br/> |
|SPO_TeamFileSharedInternally  <br/> |Numero di file che l'utente ha condiviso internamente da un sito del team o con utenti all'interno di gruppi (che potrebbero includere utenti esterni).  <br/> |
|SPO_TeamFileSharedExternally  <br/> |Numero di file che l'utente ha condiviso esternamente da un sito del team.  <br/> |
|SPO_TeamAccessByOwner  <br/> |Numero di file con cui l'utente ha interagito e che si trovano in un sito del team di cui è proprietario.  <br/> |
|SPO_TeamAccessByOthers  <br/> |Numero di file con cui l'utente ha interagito e che si trovano in un sito del team di cui è proprietario un altro utente.  <br/> |
|Teams_ChatMessages  <br/> |Numero di messaggi di chat inviati.  <br/> |
|Teams_ChannelMessage  <br/> |Numero di messaggi inviati ai canali.  <br/> |
|Teams_CallParticipate  <br/> |Numero di chiamate a cui l'utente ha partecipato.  <br/> |
|Teams_MeetingParticipate  <br/> |Numero di riunioni in cui l'utente ha partecipato.  <br/> |
|Teams_HasOtherAction  <br/> |Valore booleano se l'utente ha eseguito altre azioni in Microsoft teams.  <br/> |
|YAM_MessagePost  <br/> |Numero di messaggi di Yammer pubblicati dall'utente.  <br/> |
|YAM_MessageLiked  <br/> |Numero di messaggi di Yammer a cui l'utente ha aggiunto Mi piace.  <br/> |
|YAM_MessageRead  <br/> |Numero di messaggi di Yammer letti dall'utente.  <br/> |
|SFB_P2PSummary  <br/> |Numero di sessioni peer-to-peer a cui l'utente ha partecipato.  <br/> |
|SFB_ConfOrgSummary  <br/> |Numero di sessioni di conferenza organizzate dall'utente.  <br/> |
|SFB_ConfPartSummary  <br/> |Numero di sessioni di conferenza a cui l'utente ha partecipato.  <br/> |
   
### <a name="data-table---tenant-product-usage"></a>Tabella di dati - Tenant Product Usage

In questa tabella sono disponibili i dati relativi all'adozione mensile in termini di abilitazione, attivazione, restituzione e primo tempo degli utenti per ogni prodotto all'interno di Microsoft 365. Il valore Microsoft 365 rappresenta l'utilizzo attivo in uno dei prodotti.
  
|**Nome colonna**|**Descrizione della colonna**|
|:-----|:-----|
|Product  <br/> |Nomi dei prodotti per cui vengono riepilogate le informazioni sull'utilizzo. Il valore Microsoft 365 nella colonna Product rappresenta l'attività in uno qualsiasi dei prodotti  <br/> |
|Timeframe  <br/> |Valore del mese. Ci sarà una riga per ogni prodotto al mese per gli ultimi 12 mesi tra cui il mese corrente parziale.  <br/> |
|EnabledUsers  <br/> |Numero di utenti abilitati all'uso del prodotto per il valore dell'intervallo di tempo; se un utente è stato abilitato per la parte del mese, viene comunque conteggiato.  <br/> |
|ActiveUsers  <br/> |Numero di utenti che hanno eseguito un'attività intenzionale nel prodotto per il valore dell'intervallo di tempo.  <br/> Un utente viene considerato attivo per un prodotto per un determinato mese se ha eseguito una delle attività principali nel prodotto. Le attività chiave sono disponibili nella tabella **Tenant Product Activity**.  <br/> |
|CumulativeActiveUsers  <br/> |Numero di utenti che sono abilitati a usare un prodotto e lo hanno usato fino al mese dell'intervallo di tempo almeno una volta dopo l'inizio della raccolta dei dati nel nuovo sistema di gestione.  <br/> |
|MoMReturningUsers  <br/> |Numero di utenti che sono attivi nel mese dell'intervallo di tempo e lo erano anche nel mese precedente.  <br/> |
|FirstTimeUsers  <br/> |Numero di utenti che sono attivi nel mese dell'intervallo di tempo e che lo erano anche nel mese precedente.  <br/> Un utente viene considerato come nuovo utente in un determinato mese, se la sua attività viene rilevata per la prima volta dall'inizio della raccolta dei dati in questo nuovo sistema di registrazione. Un utente non verrà più considerato nuovo se è già stato incluso in questo gruppo, anche se è trascorso molto tempo tra le attività eseguite  <br/> |
|Content Date  <br/> |Se l'intervallo di tempo mostra il mese corrente, questo valore rappresenterà l'ultima data del mese corrente per cui i dati sono disponibili.  <br/> Se l'intervallo di tempo mostra il mese precedente, questo valore rappresenterà l'ultima data del mese dell'intervallo di tempo.  <br/> |
   
### <a name="data-table---tenant-product-activity"></a>Tabella di dati - Tenant Product Activity

Questa tabella fornisce i totali mensili delle attività e il numero di utenti attivi per varie attività all'interno dei prodotti.
  
|**Nome colonna**|**Descrizione della colonna**|
|:-----|:-----|
|Timeframe  <br/> |Valore del mese. Ci sarà una riga per ogni prodotto al mese per gli ultimi 12 mesi tra cui il mese corrente parziale.  <br/> |
|Prodotto  <br/> |Nome del prodotto all'interno di Microsoft 365 per il quale sono disponibili i dati di utilizzo.  <br/> |
|Attività  <br/> |Nome dell'attività in un prodotto usato per presentare un uso attivo del prodotto.  <br/> |
|ActivityCount  <br/> |Numero totale di azioni conteggiate per ogni attività eseguita all'interno del prodotto per tutti gli utenti attivi.  <br/> **Nota:** per le attività di SharePoint Online e OneDrive for Business questo valore rappresenta il numero di singoli documenti con cui gli utenti hanno interagito.  <br/> |
|ActiveUserCount  <br/> |Numero di utenti che hanno eseguito l'attività all'interno del prodotto.  <br/> |
|TotalDurationInMinute  <br/> |Durata in minuti tra tutti gli utenti attivi che hanno usato la sessione audio o video in un'attività di Skype for Business applicabile.  <br/> |
|Content Date  <br/> |Se l'intervallo di tempo mostra il mese corrente, questo valore rappresenterà l'ultima data del mese corrente per cui i dati sono disponibili.  <br/> Se l'intervallo di tempo mostra il mese precedente, questo valore rappresenterà l'ultima data del mese dell'intervallo di tempo.  <br/> |
   
### <a name="data-table---tenant-mailbox-usage"></a>Tabella di dati - Tenant Mailbox Usage

Questa tabella è costituita dai dati di riepilogo per tutti gli utenti di Exchange Online con licenza che hanno cassette postali utente. Contiene lo stato alla fine del mese per tutte le cassette postali utente. I dati in questa tabella non sono additivi tra i vari mesi. I dati dell'ultimo mese in questa tabella rappresentano lo stato più recente.
  
|**Nome colonna**|**Descrizione della colonna**|
|:-----|:-----|
|TotalMailboxes  <br/> |Numero di cassette postali utente per l'abbonamento a Microsoft 365.  <br/> |
|IssueWarningQuota  <br/> |Quota totale per l'invio di avvisi in tutte le cassette postali degli utenti.  <br/> |
|ProhibitSendQuota  <br/> |Quota totale per impedire l'invio a tutte le cassette postali degli utenti.  <br/> |
|ProhibitSendReceiveQuota  <br/> |Quota totale per impedire l'invio/la ricezione a tutte le cassette postali degli utenti.  <br/> |
|TotalItemBytes  <br/> |Spazio di archiviazione usato per tutte le cassette postali utente in byte.  <br/> |
|MailboxesNoWarning  <br/> |Numero di cassette postali utente che si trovano sotto il limite per l'avviso sullo spazio di archiviazione.  <br/> |
|MailboxesIssueWarning  <br/> |Numero di cassette postali utente per le quali è stato inviato un messaggio di avviso relativo alla quota di archiviazione.  <br/> |
|MailboxesExceedSendQuota  <br/> |Numero di cassette postali utente che hanno superato la quota di invii.  <br/> |
|MailboxesExceedSendReceiveQuota  <br/> |Numero di cassette postali utente che hanno superato la quota di invii/ricezioni.  <br/> |
|DeletedMailboxes  <br/> |Numero di cassette postali degli utenti eliminate nell'intervallo di tempo.  <br/> |
|Timeframe  <br/> |Valore del mese.  <br/> |
|Content Date  <br/> |Se l'intervallo di tempo mostra il mese corrente, questo valore rappresenterà l'ultima data del mese corrente per cui i dati sono disponibili.  <br/> Se l'intervallo di tempo mostra il mese precedente, questo valore rappresenterà l'ultima data del mese dell'intervallo di tempo.  <br/> |
   
### <a name="data-table---tenant-client-usage"></a>Tabella di dati - Tenant Client Usage

Questa tabella contiene i dati di riepilogo mensili relativi ai client usati dagli utenti per connettersi a Exchange Online, Skype for Business e Yammer. Questa tabella non contiene ancora dati sull'utilizzo client per SharePoint Online e OneDrive for Business.
  
|**Nome colonna**|**Descrizione della colonna**|
|:-----|:-----|
|Product  <br/> |Nome del prodotto all'interno di Microsoft 365 per il quale sono disponibili i dati di utilizzo del client.  <br/> |
|ClientId  <br/> |Nome di ogni dispositivo usato per connettersi al prodotto.  <br/> |
|UserCount  <br/> |Numero di utenti che hanno usato ciascuno dei client per ogni applicazione.  <br/> |
|Timeframe  <br/> |Valore del mese  <br/> |
|Content Date  <br/> |Se l'intervallo di tempo mostra il mese corrente, questo valore rappresenterà l'ultima data del mese corrente per cui i dati sono disponibili.  <br/> Se l'intervallo di tempo mostra il mese precedente, questo valore rappresenterà l'ultima data del mese dell'intervallo di tempo.  <br/> |
   
### <a name="data-table---tenant-sharepoint-online-usage"></a>Tabella di dati - Tenant SharePoint Online Usage

Questa tabella contiene i dati di riepilogo mensili relativi all'utilizzo o alle attività dei siti di SharePoint Online. Copre solo i siti del team e del gruppo. Lo stato alla fine del mese dei siti di SharePoint Online viene rappresentato in questa colonna, ad esempio se un utente ha creato 5 documenti usando 10 MB di spazio di archiviazione totale, quindi ha eliminato alcuni file e ne ha aggiunti altri fino ad arrivare alla fine del mese a 7 file totali che usano 5 MB di spazio di archiviazione, il valore rappresentato in questa tabella è lo stato alla fine del mese. Questa tabella è nascosta per evitare i conteggi duplicati delle aggregazioni e viene usata come origine per creare due tabelle di riferimento.
  
|**Nome colonna**|**Descrizione della colonna**|
|:-----|:-----|
|SiteType  <br/> |Valore per il tipo di sito (qualsiasi/team/gruppo) (qualsiasi rappresenta uno degli altri due tipi di sito).  <br/> |
|TotalSites  <br/> |Numero di siti presenti alla fine dell'intervallo di tempo.  <br/> |
|DocumentCount  <br/> |Numero totale di documenti presenti nel sito alla fine dell'intervallo di tempo.  <br/> |
|Diplaned  <br/> |Somma dello spazio di archiviazione totale in tutti i siti alla fine dell'intervallo di tempo.  <br/> |
|ActivityType  <br/> |Numero di siti che registrano i vari tipi di attività sui file (qualsiasi/file attivi/file condivisi esternamente/file condivisi internamente/file sincronizzati).  <br/> "Qualsiasi" rappresenta qualsiasi attività di file eseguita.  <br/> |
|SitesWithOwnerActivities  <br/> |Numero dei siti attivi, in cui il proprietario del sito ha eseguito una specifica attività sui file dei propri siti.  <br/> |
|SitesWithNonOwnerActivities  <br/> |Somma dei siti attivi per il mese specificato, in cui gli utenti non proprietari del sito hanno eseguito una specifica attività sui file dei siti.  <br/> |
|ActivityTotalSites  <br/> |Numero di siti che hanno registrato attività durante l'intervallo di tempo. Se un sito ha registrato attività all'inizio dell'intervallo di tempo ed è poi stato eliminato prima della sua fine, verrà comunque conteggiato nel totale dei siti attivi per tale intervallo di tempo.  <br/> |
|Timeframe  <br/> |Questa colonna contiene il valore di data. Usato come relazione Molti-a-uno per la tabella Calendar.  <br/> |
|Content Date  <br/> |Se l'intervallo di tempo mostra il mese corrente, questo valore rappresenterà l'ultima data del mese corrente per cui i dati sono disponibili.  <br/> Se l'intervallo di tempo mostra il mese precedente, questo valore rappresenterà l'ultima data del mese dell'intervallo di tempo.  <br/> |
   
### <a name="data-table---tenant-onedrive-usage"></a>Tabella di dati-utilizzo del tenant OneDrive

Questa tabella fornisce i dati sugli account di OneDrive, come il numero di account, il numero di documenti in tutti gli account di OneDrive, lo spazio di archiviazione usato, il numero di file per tipo di attività. Lo stato alla fine del mese degli account di OneDrive for Business viene rappresentato in questa tabella. Ad esempio, se un utente ha creato 5 documenti usando 10 MB di spazio di archiviazione totale, quindi ha eliminato alcuni file e ne ha aggiunti altri fino ad arrivare alla fine del mese a 7 file totali che usano 5 MB di spazio di archiviazione, il valore rappresentato in questa tabella è lo stato alla fine del mese.
  
|**Nome colonna**|**Descrizione della colonna**|
|:-----|:-----|
|SiteType  <br/> |Il valore è "OneDrive".  <br/> |
|TotalSites  <br/> |Numero di account di OneDrive for Business presenti alla fine dell'intervallo di tempo.  <br/> |
|DocumentCount  <br/> |Numero totale dei documenti presenti in tutti gli account di OneDrive for Business alla fine dell'intervallo di tempo  <br/> |
|Diplaned  <br/> |Somma dello spazio di archiviazione totale in tutti gli account di OneDrive alla fine dell'intervallo di tempo.  <br/> |
|ActivityType  <br/> |Numero di account che registrano i vari tipi di attività sui file (qualsiasi/file attivi/file condivisi esternamente/file condivisi internamente/file sincronizzati).  <br/> "Qualsiasi" rappresenta qualsiasi attività di file eseguita  <br/> |
|SitesWithOwnerActivities  <br/> |Numero di account attivi di OneDrive for Business, in cui il proprietario dell'account ha eseguito una specifica attività sui file del proprio account.  <br/> |
|SitesWithNonOwnerActivities  <br/> |Numero di account di OneDrive for Business in cui sono state eseguite attività sui file da utenti diversi dal proprietario.  <br/> |
|ActivityTotalSites  <br/> |Numero di account di OneDrive for Business che hanno registrato attività durante l'intervallo di tempo. Se un account di OneDrive for Business ha registrato attività all'inizio dell'intervallo di tempo ed è poi stato eliminato prima della sua fine, verrà comunque conteggiato nell'account attivo di OneDrive for Business per tale intervallo di tempo.  <br/> |
|Timeframe  <br/> |Questa colonna contiene il valore di data. Usato come relazione Molti-a-uno per la tabella Calendar.  <br/> |
|Content Date  <br/> |Se l'intervallo di tempo mostra il mese corrente, questo valore rappresenterà l'ultima data del mese corrente per cui i dati sono disponibili.  <br/> Se l'intervallo di tempo mostra il mese precedente, questo valore rappresenterà l'ultima data del mese dell'intervallo di tempo.  <br/> |
   
### <a name="data-table---tenant-microsoft-365-groups-usage"></a>Tabella di dati-tenant Microsoft 365 groups Usage

In questa tabella sono disponibili i dati su come vengono utilizzati i gruppi Microsoft 365 nell'organizzazione.
  
****

|**Nome colonna**|**Descrizione della colonna**|
|:-----|:-----|
|Tempi  <br/> |Valore del mese. Ci sarà una riga per ogni prodotto al mese per gli ultimi 12 mesi tra cui il mese corrente parziale.  <br/> |
|GroupType  <br/> |Tipo di gruppo (privato/pubblico/qualsiasi).  <br/> |
|TotalGroups  <br/> |Numero di gruppi di ogni tipo di gruppo.  <br/> |
|ActiveGroups  <br/> |Numero di gruppi attivi.  <br/> |
|MBX_TotalGroups  <br/> |Numero di gruppi di cassette postali.  <br/> |
|MBX_ActiveGroups  <br/> |Numero di gruppi di cassette postali attivi.  <br/> |
|MBX_TotalActivities  <br/> |Numero di attività delle cassette postali.  <br/> |
|MBX_TotalItems  <br/> |Numero di elementi delle cassette postali.  <br/> |
|MBX_StorageUsed  <br/> |Quantità di spazio di archiviazione delle cassette postali utilizzato.  <br/> |
|SPO_TotalGroups  <br/> |Numero di gruppi di SharePoint.  <br/> |
|SPO_ActiveGroups  <br/> |Numero di gruppi di SharePoint attivi.  <br/> |
|SPO_FileAccessedActiveGroups  <br/> |Numero di gruppi di SharePoint che dispongono di attività di accesso ai file.  <br/> |
|SPO_FileSyncedActiveGroups  <br/> |Numero di gruppi di SharePoint che dispongono di attività di sincronizzazione dei file.  <br/> |
|SPO_FileSharedInternallyActiveGroups  <br/> |Numero di gruppi di SharePoint che dispongono di attività condivise internamente o con gruppi (che possono includere utenti esterni).  <br/> |
|SPO_FileSharedExternallyActiveGroups  <br/> |Numero di gruppi di SharePoint che hanno condiviso attività esterne.  <br/> |
|SPO_TotalActivities  <br/> |Numero di attività di SharePoint.  <br/> |
|SPO_FileAccessedActivities  <br/> |Numero di attività di accesso ai file di SharePoint.  <br/> |
|SPO_FileSyncedActivities  <br/> |Numero di attività di sincronizzazione dei file di SharePoint.  <br/> |
|SPO_FileSharedInternallyActivities  <br/> |Il numero di attività condivise di file di SharePoint internamente o con gruppi (che possono includere membri esterni).  <br/> |
|SPO_FileSharedExternallyActivities  <br/> |Numero di attività di SharePoint di file condivise esternamente.  <br/> |
|SPO_TotalFiles  <br/> |Numero di file di SharePoint.  <br/> |
|SPO_ActiveFiles  <br/> |Numero di file di SharePoint attivi.  <br/> |
|SPO_StorageUsed  <br/> |Quantità di spazio di archiviazione di SharePoint utilizzato.  <br/> |
|YAM_TotalGroups  <br/> |Numero di gruppi di Yammer.  <br/> |
|YAM_ActiveGroups  <br/> |Numero di gruppi di Yammer attivi.  <br/> |
|YAM_LikedActiveGroups  <br/> |Numero di gruppi di Yammer che hanno attività simili.  <br/> |
|YAM_PostedActiveGroups  <br/> |Numero di gruppi di Yammer che dispongono di attività postali.  <br/> |
|YAM_ReadActiveGroups  <br/> |Numero di gruppi di Yammer che dispongono di attività di lettura.  <br/> |
|YAM_TotalActivities  <br/> |Numero di attività di Yammer.  <br/> |
|YAM_LikedActivities  <br/> |Numero di attività di tipo Yammer.  <br/> |
|YAM_PostedActivties  <br/> |Numero di attività postali di Yammer.  <br/> |
|YAM_ReadActivites  <br/> |Numero di attività di lettura di Yammer.  <br/> |
   
### <a name="data-table---tenant-office-activation"></a>Tabella di dati - Tenant Office Activation

La tabella fornisce i dati sul numero di attivazioni dell'abbonamento a Office in tutti i piani di servizio, ad esempio Office Proplus, Visio, Project. Fornisce anche i dati sul numero di attivazioni per ogni dispositivo (Android/iOS/Mac/PC).
  
|**Nome colonna**|**Descrizione della colonna**|
|:-----|:-----|
|ServicePlanName  <br/> |Elenco dei valori del nome del piano di servizio e numero di attivazioni per dispositivi, come rappresentati nelle colonne successive.  <br/> |
|TotalEnabled  <br/> |Numero di utenti abilitati per ogni piano di servizio entro la fine dell'intervallo di tempo.  <br/> |
|TotalActivatedUsers  <br/> |Numero di utenti che hanno attivato ogni piano di servizio entro la fine dell'intervallo di tempo.  <br/> |
|AndroidCount  <br/> |Numero di attivazioni per ogni piano di servizio per dispositivi Android entro la fine dell'intervallo di tempo.  <br/> |
|iOSCount  <br/> |Numero di attivazioni per ogni piano di servizio per dispositivi iOS entro la fine dell'intervallo di tempo.  <br/> |
|MacCount  <br/> |Numero di attivazioni per ogni piano di servizio per dispositivi MAC entro la fine dell'intervallo di tempo.  <br/> |
|PcCount  <br/> |Numero di attivazioni per ogni piano di servizio per dispositivi PC entro la fine dell'intervallo di tempo.  <br/> |
|WinRtCount  <br/> |Numero di attivazioni per ogni piano di servizio per dispositivi Windows Mobile entro la fine dell'intervallo di tempo.  <br/> |
|Timeframe  <br/> |Questa colonna contiene il valore di data. Usato come relazione Molti-a-uno per la tabella Calendar.  <br/> |
|Content Date  <br/> |Se l'intervallo di tempo mostra il mese corrente, questo valore rappresenterà l'ultima data del mese corrente per cui i dati sono disponibili.  <br/> Se l'intervallo di tempo mostra il mese precedente, questo valore rappresenterà l'ultima data del mese dell'intervallo di tempo.  <br/> |
   

