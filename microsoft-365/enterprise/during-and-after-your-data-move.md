---
title: Durante e dopo lo spostamento dati
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.collection: SPO_Content
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: f47e3e09-b1dc-4b80-b6ea-fd6e0933407f
f1.keywords:
- NOCSH
description: Gli spostamenti di dati sono operazioni back-end che si verificano quando Microsoft sposta i servizi e i dati associati per il tenant in un nuovo datacenter Geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9f87628d6bbc65fe4122999f6d0fde809fed51b8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691161"
---
# <a name="during-and-after-your-data-move"></a>Durante e dopo lo spostamento dati

Gli spostamenti di dati sono un'operazione back-end con un impatto minimo sugli utenti finali. Non è necessaria alcuna azione mentre Microsoft sposta ogni servizio e i dati associati per il tenant in un nuovo datacenter Geo. Il trasferimento e la convalida dei dati avvengono in background in anticipo con un impatto minimo per gli utenti.
  
> [!NOTE]
> Gli spostamenti si verificano in momenti diversi per ogni servizio. Di conseguenza, si vedrà la funzionalità ridotta descritta per ogni servizio in un'ora diversa. 
  
Guardare il centro messaggi di Microsoft 365 per conferma quando si sposta per ogni di Exchange Online, SharePoint Online, teams e Skype for business sono stati completati. Come illustrato nella tabella seguente, è possibile richiedere fino a 24 mesi, dopo la fine del periodo di registrazione, per completare tutti gli spostamenti di dati richiesti per tutti i clienti in uno specifico Geo. Se dopo lo spostamento vengono visualizzati problemi con il tenant, contattare il [supporto tecnico](https://go.microsoft.com/fwlink/p/?LinkID=522459) per ottenere assistenza. 
  

|**Clienti con paese di registrazione in**|**Tutti gli spostamenti completati da**|
|:-----|:-----|
|Australia, Nuova Zelanda, Figi  <br/> |Luglio 1, 2022  <br/> |
|Giappone  <br/> |Luglio 1, 2022  <br/> |
|India  <br/> |Luglio 1, 2022  <br/> |
|Canada  <br/> |Luglio 1, 2022  <br/> |
|Corea del Sud  <br/> |Luglio 1, 2022  <br/> |
|Regno Unito  <br/> |Luglio 1, 2022  <br/> |
|Francia  <br/> |Luglio 1, 2022  <br/> |
|Emirati Arabi Uniti  <br/> |Luglio 1, 2022  <br/> |
|Sudafrica  <br/> |Luglio 1, 2022  <br/> |
|Svizzera, Liechtenstein  <br/> |Luglio 1, 2022  <br/> |
|Germania  <br/> |Pianificata  <br/> |
|Norvegia  <br/> |2022 novembre 1  <br/> |

## <a name="exchange-online"></a>Exchange Online

Poiché richiede tempo per spostare ogni utente nel nuovo datacenter Geo per un singolo tenant, alcuni utenti saranno comunque nel centro dati geografico precedente durante lo spostamento, mentre altri saranno nel nuovo datacenter Geo. Questo significa che alcune caratteristiche che implicano l'accesso a più cassette postali potrebbero non funzionare completamente durante il processo di spostamento, che può durare settimane. Queste funzionalità sono descritte nelle sezioni seguenti.
  
### <a name="open-shared-folder-in-outlook-web-access"></a>Aprire "cartella condivisa" in Outlook Web Access

Alcuni utenti aprono una cartella di posta condivisa da un'altra cassetta postale (che l'utente dispone di autorizzazioni di lettura o scrittura) in Outlook Web Access utilizzando la caratteristica "cartella condivisa". Nella tabella seguente viene descritto in che modo l'accesso alle cartelle condivise funziona durante lo spostamento di una cassetta postale. Tenere presente che gli utenti con autorizzazioni complete per una cassetta postale condivisa possono aprire la cassetta postale utilizzando Outlook Web Access durante lo spostamento. 
  
|**Configurazione**|**Descrizione**|
|:-----|:-----|
|L'utente dispone dell'autorizzazione cartella cassetta postale per un'altra cassetta postale  <br/> |Potenzialmente limitata.  <br/> Se l'utente A e la cassetta postale B non sono nello stesso Geo durante lo spostamento del tenant, l'utente A non è in grado di aprire la cartella della cassetta postale B in Outlook Web Access se l'utente A ha l'autorizzazione solo per una cartella specifica nella cassetta postale B.  <br/> Per aggiungere una cartella condivisa, fare clic con il pulsante destro del mouse sul nome utente nel riquadro di spostamento a sinistra e selezionare **Aggiungi cartella condivisa**.  <br/> |
|Utente con autorizzazione completa alle cassette postali per un'altra cassetta postale  <br/> |Pienamente supportato.  <br/> Se l'utente a dispone dell'autorizzazione di accesso completo alla cassetta postale B, l'utente A può fare clic sulla cartella condivisa nel riquadro di spostamento a sinistra in Outlook Web Access per aprire una finestra in cui viene visualizzata la cassetta postale B.  Un utente può aprire una cassetta postale condivisa utilizzando Outlook Web Access durante lo spostamento senza alcun impatto negativo. La limitazione si applica solo alla condivisione a livello di cartella in una cassetta postale.           |
  
## <a name="sharepoint-online"></a>SharePoint Online

Quando viene spostato SharePoint Online, vengono spostati anche i dati per i servizi seguenti:
  
- One Drive for Business
    
- Project Online
    
- Project per Microsoft 365
    
- Servizi video Microsoft 365
    
- Office nel browser s
    
- Microsoft 365 Apps for enterprise
    
- Visio Pro per Microsoft 365
    
Dopo aver completato lo spostamento dei dati di SharePoint Online, è possibile che vengano visualizzati alcuni degli effetti riportati di seguito.
  
### <a name="microsoft-365-video-services"></a>Servizi video Microsoft 365

- Lo spostamento dei dati per il video richiede più tempo degli spostamenti per il resto del contenuto in SharePoint Online.
    
- Dopo aver spostato il contenuto di SharePoint Online, si verificherà un intervallo di tempo quando i video non sono in grado di essere riprodotti.
    
- Si stanno rimuovendo le copie Trans-coded dal Data Center precedente e la loro transcodifica nel nuovo datacenter.
    
### <a name="search"></a>Ricerca

Durante lo spostamento dei dati di SharePoint Online, la migrazione dell'indice di ricerca e delle impostazioni di ricerca in una nuova posizione. Fino a quando non è stato **completato** lo spostamento dei dati di SharePoint Online, è possibile continuare a servire gli utenti dall'indice nel percorso originale. Nella nuova posizione viene avviata automaticamente la ricerca per indicizzazione del contenuto dopo aver completato lo spostamento dei dati di SharePoint Online. Da questo punto in poi, vengono serviti gli utenti dall'indice migrato. Le modifiche al contenuto che si sono verificate dopo la migrazione non vengono incluse nell'indice migrato finché la ricerca per indicizzazione non viene rilevata. La maggior parte dei clienti non si accorge che i risultati sono meno freschi subito dopo aver completato lo spostamento dei dati di SharePoint Online, ma alcuni clienti potrebbero riscontrare una riduzione della freschezza nelle prime 24-48 ore. 
  
Le seguenti funzionalità di ricerca sono intaccate:
  
- Risultati della ricerca e Web part di ricerca: i risultati non includono le modifiche che si sono verificate dopo la migrazione fino alla ricerca per indicizzazione. 
    
- Approfondire: l'approfondimento non include le modifiche apportate dopo la migrazione fino alla ricerca per indicizzazione.
    
- Popularity and search Reports for the site: counts for Excel Reports nella nuova posizione sono disponibili solo i conteggi migrati e i conteggi dei rapporti sull'utilizzo che sono stati eseguiti dopo aver completato lo spostamento dei dati di SharePoint Online. Tutti i conteggi del periodo intermedio sono persi e non possono essere recuperati. Questo periodo è in genere un paio di giorni. Alcuni clienti potrebbero subire perdite più brevi o più lunghe.
    
- Portale video: la visualizzazione conta e le statistiche per il portale video dipendono dalle statistiche per i report di Excel, quindi i conteggi e le statistiche di visualizzazione per il portale video vengono persi per lo stesso periodo di tempo per i report di Excel.
    
- eDiscovery: gli elementi che sono stati modificati durante la migrazione non vengono visualizzati finché la ricerca per indicizzazione riprende le modifiche.
    
- Protezione dalla perdita di dati (DLP): i criteri non vengono applicati sugli elementi che cambiano finché la ricerca per indicizzazione riprende le modifiche.

## <a name="microsoft-teams"></a>Microsoft Teams

Oltre a Exchange Online, SharePoint Online e OneDrive for business, Microsoft eseguirà la migrazione dei dati del team nel datacenter locale.

- Messaggi di chat dei team, inclusi i messaggi privati e i messaggi di canale.
- Immagini di Team utilizzate nelle chat.

I file dei team sono archiviati in SharePoint Online e i file chat di team sono archiviati in OneDrive for business. La segreteria telefonica, il calendario, la cronologia chat e i contatti sono archiviati in Exchange Online. In molti casi, Exchange Online, SharePoint Online e OneDrive for business sono già utilizzati dal cliente nel centro dati geografico locale e fanno parte del programma di migrazione Microsoft 365 per i paesi idonei ai clienti.

## <a name="skype-for-business"></a>Skype for Business

Gli spostamenti di Skype for business sono disponibili per Australia, Giappone, India, Canada, Regno Unito e Corea del sud.

Tutti gli utenti verranno disconnessi dal software client Skype for business durante il ritaglio. L'accesso automatico ricollegherà gli utenti entro due minuti.
  
|**Caratteristiche che funzionano durante l'intero spostamento**|**Caratteristiche che possono essere limitate durante una parte dello spostamento**|
|:-----|:-----|
| Messaggistica istantanea e chiamate vocali  <br/>  Gli utenti possono aggiungere contatti, aggiungere gruppi di contatti, aggiungere riunioni, impostare la propria posizione e cambiare "cosa succede oggi".  <br/>  Le impostazioni del provider di servizi di audioconferenza (ACP) vengono copiate nel datacenter di destinazione Geo. Se il provider ACP è presente nel datacenter di destinazione, funzionerà. In caso contrario, non verrà.  <br/> | L'amministratore tenant TRPS (tenant Remote PowerShell) non sarà disponibile per gli amministratori per la creazione di sessioni.  <br/>  L'amministratore tenant LAC non sarà disponibile per l'accesso degli amministratori e per modificare le impostazioni dell'utente.  <br/> |
   
|**Dopo lo spostamento**|
|:-----|
| I dati relativi alle riunioni (presentazioni caricate e così via) non verranno spostati e dovranno essere caricati di nuovo.  <br/>  I client Lync meno recenti, ad esempio client Lync 2010 e client Lync per Mac 2011, sono noti per memorizzare nella cache le informazioni DNS sul servizio che causano problemi di accesso. La cancellazione della cache DNS potrebbe essere necessaria se l'utente non è nel client Windows Skype for business più recente. Consultare [risoluzione dei problemi relativi alla configurazione DNS di Skype for business online in Office 365](https://docs.microsoft.com/skypeforbusiness/troubleshoot/online-configuration/dns-configuration-issue). Gli utenti di Lync per Mac client devono seguire [queste istruzioni](https://support.microsoft.com/kb/2629861).  <br/> |
   
### <a name="skype-for-business-moves-that-involve-a-third-party-audio-conferencing-provider"></a>Spostamenti di Skype for business che coinvolgono un provider di servizi di audioconferenza di terze parti
I servizi per i componenti aggiuntivi di terze parti per le conferenze telefoniche per Skype for business non sono disponibili per gli utenti ospitati in nuovi Data Center geografici specifici.  I clienti esistenti che utilizzano un servizio di provider di servizi di audioconferenza di terze parti non devono richiedere lo spostamento in un nuovo Data Center geografico specifico.  Per utilizzare un provider di servizi di audioconferenza di terze parti, è necessario che i nuovi clienti distribuiti nei nuovi Data Center geografici richiedano uno spostamento in un Data Center regionale.
  
## <a name="related-topics"></a>Argomenti correlati 
 
[Come richiedere lo spostamento dati](request-your-data-move.md)
    
[Domande frequenti sullo spostamento dati](data-move-faq.md)
  
[Nuovo datacenter GEOS per Microsoft Dynamics CRM Online](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[Servizi di Azure in base all'area geografica](https://azure.microsoft.com/regions/)
