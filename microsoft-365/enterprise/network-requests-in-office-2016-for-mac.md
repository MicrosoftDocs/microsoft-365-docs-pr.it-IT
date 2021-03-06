---
title: Richieste di rete in Office per Mac
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/9/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOM160
ms.assetid: afdae969-4046-44b9-9adb-f1bab216414b
description: In questo articolo vengono descritti gli endpoint e gli URL Office per Mac che le applicazioni tentano di raggiungere e i servizi forniti.
ms.openlocfilehash: b777b4ea7e03495cb6389be8fe05e96a26fd9664
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691269"
---
# <a name="network-requests-in-office-for-mac"></a>Richieste di rete in Office per Mac

Office per Mac applicazioni offrono un'esperienza di app nativa sulla piattaforma macOS. Ogni app è progettata per funzionare in diversi scenari, inclusi gli stati in cui non è disponibile alcun accesso alla rete. Quando un computer è connesso a una rete, le applicazioni si connettono automaticamente a una serie di servizi basati sul Web per fornire funzionalità avanzate. Le informazioni seguenti descrivono gli endpoint e gli URL che le applicazioni tentano di raggiungere e i servizi forniti. Queste informazioni sono utili per la risoluzione dei problemi di configurazione della rete e l'impostazione dei criteri per i server proxy di rete. I dettagli in questo articolo sono destinati a integrare l'articolo relativo [all'URL](urls-and-ip-address-ranges.md)Office 365 e agli intervalli di indirizzi, che include gli endpoint per i computer che eseguono Microsoft Windows. Se non specificato, le informazioni contenute in questo articolo si applicano anche a Office 2019 per Mac e Office 2016 per Mac, che sono disponibili come acquisto una sola volta presso un punto vendita o tramite un contratto multilicenza. 

  
La maggior parte di questo articolo contiene tabelle che illustrano in dettaglio GLI URL di rete, il tipo e la descrizione del servizio o della funzionalità fornita da tale endpoint. Ognuna delle app Office può differire per l'utilizzo del servizio e dell'endpoint. Le app seguenti sono definite nelle tabelle seguenti:
  
- W: Word
- P: PowerPoint
- X: Excel
- O: Outlook
- N: OneNote
   
Il tipo di URL è definito come segue:
  
- ST: Static - L'URL è hard-coded nell'applicazione client.
    
- SS: Semi-Static - L'URL viene codificato come parte di una pagina Web o di un redirector.
    
- CS: Config Service - L'URL viene restituito come parte del Office Configuration Service.

    
## <a name="office-for-mac-default-configuration"></a>Office per Mac configurazione predefinita

 **Installazione e aggiornamenti**
  
Gli endpoint di rete seguenti vengono usati per scaricare il programma Office per Mac di installazione da Microsoft rete per la distribuzione di contenuti (rete CDN).
  
|**URL**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|```https://go.microsoft.com/fwlink/```  <br/> |ST  <br/> |Microsoft 365 Servizio di collegamento di inoltro del portale di installazione ai pacchetti di installazione più recenti.  <br/> |
|```https://officecdn-microsoft-com.akamaized.net/```  <br/> |SS  <br/> |Percorso dei pacchetti di installazione nel rete per la distribuzione di contenuti.  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |SS  <br/> |Percorso dei pacchetti di installazione nel rete per la distribuzione di contenuti.  <br/> |
|```https://officeci-mauservice.azurewebsites.net/```  <br/> |ST  <br/> |Endpoint di controllo di gestione per Microsoft AutoUpdate  <br/> |
   
 **Primo avvio dell'app**
  
Gli endpoint di rete seguenti vengono contattati al primo avvio di un app Office. Questi endpoint forniscono funzionalità Office per gli utenti e gli URL vengono contattati indipendentemente dal tipo di licenza (incluse le installazioni con contratti multilicenza).
  
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://config.edge.skype.com/```  <br/> |WXPON  <br/> |ST  <br/> |Configurazione di "flighting": consente l'illuminazione e la sperimentazione delle funzionalità.  <br/> |
|```https://ocos-office365-s2s.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |Test di configurazione di rete in "flighting"  <br/> |
|```https://client-office365-tas.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |Test di configurazione di rete in "flighting"  <br/> |
|```https://officeclient.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office Servizio di configurazione - Elenco master degli endpoint del servizio.  <br/> |
|```https://nexusrules.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office Download della telemetria delle regole - Informa il client sui dati e gli eventi da caricare nel servizio di telemetria.  <br/> |
|```https://mobile.pipe.aria.microsoft.com/```  <br/> |N  <br/> |CS  <br/> |OneNote Servizio di telemetria  <br/> |
|```https://nexus.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office Telemetry Upload Reporting - Gli eventi di errore e heartbeart che si verificano nel client vengono caricati nel servizio di telemetria.  <br/> |
|```https://templateservice.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Office Servizio modelli: fornisce agli utenti modelli di documento online.  <br/> |
|```https://omextemplates.content.office.net/```  <br/> |WXP  <br/> |CS  <br/> |Office Download modelli : Archiviazione di immagini modello PNG.  <br/> |
|```https://store.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Configurazione dello Store per Office app.  <br/> |
|```https://odc.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Office Document Integration Services Catalog (elenco di servizi ed endpoint) e Individuazione area di autenticazione principale.  <br/> |
|```https://cdn.odc.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Risorse per Home Realm Discovery v2 (15.40 e versioni successive)  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Manifesti di Microsoft AutoUpdate : verifica se sono disponibili aggiornamenti  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |WXPO  <br/> |SS  <br/> |Libreria JavaScript di Microsoft Ajax  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |App Wikipedia per Office e risorse.  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Bing Eseguire il mapping dell'app Office e delle risorse.  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Utenti Graph app per Office e risorse.  <br/> |
|```https://www.onenote.com/```  <br/> |N  <br/> |ST  <br/> |Contenuto novità per OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |ST  <br/> |Nuovo contenuto per OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |SS  <br/> |What's New images for OneNote.  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |ST  <br/> |Servizio di supporto in-app.  <br/> |
|```https://prod-global-autodetect.acompli.net/```  <br/> |O  <br/> |ST  <br/> |Servizio di rilevamento account di posta elettronica.  <br/> |
|```https://autodiscover-s.outlook.com/```  <br/> |WXPO  <br/> |ST  <br/> |Outlook AutoDiscovery  <br/> |
|```https://outlook.office365.com/```  <br/> |WXPO  <br/> |ST  <br/> |Outlook endpoint per Microsoft 365 servizio.  <br/> |
|```https://r1.res.office365.com/```  <br/> |O  <br/> |ST  <br/> |Icone per Outlook componenti aggiuntivi.  <br/> |
   
> [!NOTE]
> Il Office configuration service funge da servizio di individuazione automatica per tutti Microsoft Office client, non solo per Mac. Gli endpoint restituiti nella risposta sono semi-statici in quanto la modifica è molto rara, ma comunque possibile. 
  
 **Accesso**
  
Gli endpoint di rete seguenti vengono contattati quando si accede all'archiviazione basata su cloud. A seconda del tipo di account, è possibile contattare servizi diversi. Ad esempio:
  
- **MSA: Account Microsoft** - Utilizzato in genere per scenari di consumo e vendita al dettaglio 
    
- **OrgID: Account dell'organizzazione** - Utilizzato in genere per scenari commerciali 
    
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://login.windows.net/```  <br/> |WXPON  <br/> |ST  <br/> |Windows Servizio di autorizzazione  <br/> |
|```https://login.microsoftonline.com/```  <br/> |WXPON  <br/> |ST  <br/> |Microsoft 365 Servizio di accesso (OrgID)  <br/> |
|```https://login.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Servizio di accesso all'account Microsoft (MSA)  <br/> |
|```https://auth.gfx.ms/```  <br/> |WXPON  <br/> |CS  <br/> |Microsoft Account Login Service Helper (MSA)  <br/> |
|```https://secure.aadcdn.microsoftonline-p.com/```  <br/> |WXPON  <br/> |SS  <br/> |Microsoft 365 Personalizzazione dell'accesso (OrgID)  <br/> |
|```https://ocws.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Document and Places Archiviazione Locator  <br/> |
|```https://roaming.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Servizio documenti usati più di recente  <br/> |
   
> [!NOTE]
> Per le licenze basate su sottoscrizione e per la vendita al dettaglio, l'accesso attiva il prodotto e consente l'accesso a risorse cloud come OneDrive. Per le installazioni con contratti multilicenza, agli utenti viene comunque richiesto di eseguire l'accesso (per impostazione predefinita), ma ciò è necessario solo per l'accesso alle risorse cloud, poiché il prodotto è già attivato. 
  
 **Attivazione del prodotto**
  
Gli endpoint di rete seguenti si applicano alle Microsoft 365 di sottoscrizione e licenze di vendita al dettaglio. In particolare, non si applica alle installazioni con contratti multilicenza.
  
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://ols.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Servizio gestione licenze Office  <br/> |
   
 **Contenuto Novità**
  
Gli endpoint di rete seguenti si applicano solo Microsoft 365 sottoscrizione.
  
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://contentstorage.osi.office.net/```  <br/> |WXPO  <br/> |SS  <br/> |Contenuto della pagina Novità JSON.  <br/> |
   
 **Strumento ricerche**
  
Gli endpoint di rete seguenti si applicano solo Microsoft 365 sottoscrizione.
  
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |Servizio Web ricercatore  <br/> |
|```https://cdn.entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |Contenuto statico del ricercatore  <br/> |
|```https://www.bing.com/```  <br/> |W  <br/> |CS  <br/> |Provider di contenuti ricerca  <br/> |
   
 **Ricerca intelligente**
  
Gli endpoint di rete seguenti si applicano alle Microsoft 365 di sottoscrizione e di vendita al dettaglio/contratti multilicenza.
  
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://uci.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Servizio Web Insights  <br/> |
|```https://ajax.googleapis.com/```  <br/> |WXPN  <br/> |CS  <br/> |Libreria JQuery  <br/> |
|```https://cdnjs.cloudflare.com/```  <br/> |WXPN  <br/> |CS  <br/> |Supporto della libreria JavaScript  <br/> |
|```https://www.bing.com/```  <br/> |WXPN  <br/> |CS  <br/> |Provider di contenuti Insights  <br/> |
|```https://tse1.mm.bing.net/```  <br/> |WXPN  <br/> |CS  <br/> |Provider di contenuti Insights  <br/> |
   
 **PowerPoint Designer**
  
Gli endpoint di rete seguenti si applicano solo Microsoft 365 sottoscrizione.
  
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://pptsgs.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |PowerPoint Designer Web  <br/> |
   
 **Avvio rapido di PowerPoint**
  
Gli endpoint di rete seguenti si applicano solo Microsoft 365 sottoscrizione.
  
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://pptcts.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |PowerPoint Servizio Web QuickStarter  <br/> |
   
 **Inviare un smile/cipiglio**
  
Gli endpoint di rete seguenti si applicano alle Microsoft 365 di sottoscrizione e di vendita al dettaglio/contratti multilicenza.
  
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://sas.office.microsoft.com/```  <br/> |WXPON  <br/> |CS  <br/> |Inviare un servizio Smile  <br/> |
   
 **Contattare il supporto tecnico**
  
Gli endpoint di rete seguenti si applicano alle Microsoft 365 di sottoscrizione e di vendita al dettaglio/contratti multilicenza.
  
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://powerlift-frontdesk.acompli.net/```  <br/> |O  <br/> |CS  <br/> |Contattare il servizio di supporto  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |CS  <br/> |Servizio di supporto in-app  <br/> |
   
 **Salva come PDF**
  
Gli endpoint di rete seguenti si applicano alle Microsoft 365 di sottoscrizione e di vendita al dettaglio/contratti multilicenza.
  
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://wordcs.officeapps.live.com/```  <br/> |W  <br/> |CS  <br/> |Servizio di conversione documenti di Word (PDF)  <br/> |
   
 **Office App (aka add-ins)**
  
Gli endpoint di rete seguenti si applicano Microsoft 365 le attivazioni di sottoscrizione e di vendita al dettaglio/contratti multilicenza quando Office componenti aggiuntivi dell'app sono attendibili.
  
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://store.office.com/```  <br/> |WXPO  <br/> |CS  <br/> |app Office store  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |Risorse dell'app Wikipedia  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Bing Mappare le risorse dell'app  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com```  <br/> |X  <br/> |SS  <br/> |Risorse Graph'app contatti  <br/> |
|```https://o15.officeredir.microsoft.com/```  <br/> |WPX  <br/> |SS  <br/> |Office Servizio di reindirizzamento  <br/> |
|```https://appsforoffice.microsoft.com/```  <br/> |WXP  <br/> |SS  <br/> |Office Librerie JavaScript  <br/> |
|```https://telemetry.firstpartyapps.oaspapps.com/```  <br/> |WX  <br/> |SS  <br/> |Servizio di telemetria e report per Office app  <br/> |
|```https://ajax.microsoft.com/```  <br/> |W  <br/> |SS  <br/> |Libreria JavaScript di Microsoft Ajax  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |X  <br/> |SS  <br/> |Libreria JavaScript di Microsoft Ajax  <br/> |
|```https://c.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Office Librerie JavaScript  <br/> |
|```https://c1.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Risorse di supporto  <br/> |
|```https://cs.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Risorse di supporto  <br/> |
|```https://c.bing.com/```  <br/> |WPXO  <br/> |SS  <br/> |Risorse di supporto  <br/> |
|```https://*.cdn.optimizely.com/```  <br/> |WPXO  <br/> |SS  <br/> |Libreria JavaScript  <br/> |
|```https://errors.client.optimizely.com/```  <br/> |WPX  <br/> |SS  <br/> |Segnalazione errori  <br/> |
|```https://*-contentstorage.osi.office.net/```  <br/> |WPXO  <br/> |SS  <br/> |Risorse tipo di carattere  <br/> |
|```https://nexus.ensighten.com/```  <br/> |WPXO  <br/> |SS  <br/> |Servizio di telemetria  <br/> |
|```https://browser.pipe.aria.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Report di telemetria  <br/> |
|```https://*.vo.msecnd.net/```  <br/> |WPXO  <br/> |SS  <br/> |Microsoft Store Raccolta di risorse  <br/> |
|```https://*.wikipedia.org/```  <br/> |W  <br/> |SS  <br/> |Risorse della pagina di Wikipedia  <br/> |
|```https://upload.wikimedia.org/```  <br/> |W  <br/> |SS  <br/> |Risorse multimediali di Wikipedia  <br/> |
|```https://wikipedia.firstpartyappssandbox.oappseperate.com/```  <br/> |W  <br/> |SS  <br/> |Frame sandbox di Wikipedia  <br/> |
|```https://*.virtualearth.net/```  <br/> |X  <br/> |SS  <br/> |Modelli di mappa  <br/> |
   
 **Collegamenti sicuri**
  
L'endpoint di rete seguente si applica a tutte Office solo per Microsoft 365 sottoscrizione.
  
|**URL**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|```https://*.oscs.protection.outlook.com/```  <br/> |CS  <br/> |Microsoft Safe Link Service  <br/> |
   
 **Segnalazione arresti anomalo del sistema**
  
L'endpoint di rete seguente si applica a tutte Office applicazioni per le Microsoft 365 e le attivazioni di contratti multilicenza/vendita al dettaglio. Quando un processo si arresta in modo imprevisto, viene generato un report e inviato al servizio Watson.
  
|**URL**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|```https://watson.microsoft.com/```  <br/> |ST  <br/> |Servizio Segnalazione errori Microsoft  <br/> |
|```https://officeci.azurewebsites.net/```  <br/> |ST  <br/> |Office Collaborative Insights Service  <br/> |
   
## <a name="options-for-reducing-network-requests-and-traffic"></a>Opzioni per ridurre le richieste di rete e il traffico

La configurazione predefinita di Office per Mac offre la migliore esperienza utente, sia in termini di funzionalità che per mantenere aggiornato il computer. In alcuni scenari è possibile impedire alle applicazioni di contattare gli endpoint di rete. In questa sezione vengono illustrate le opzioni per eseguire questa operazione.
  
 ### <a name="disabling-cloud-sign-in-and-office-add-ins"></a>Disabilitazione di Cloud Sign-In e Office Add-Ins
  
I clienti con contratti multilicenza possono avere criteri rigorosi sul salvataggio dei documenti nell'archiviazione basata su cloud. La seguente preferenza per applicazione può essere impostata per disabilitare l'accesso a MSA/OrgID e l'accesso Office componenti aggiuntivi.
  
- ```defaults write com.microsoft.Word UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Excel UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Powerpoint UseOnlineContent -integer 0```

Se gli utenti tentano di accedere alla Sign-In, verrà visualizzato un errore che indica che non è presente una connessione di rete. Poiché questa preferenza blocca anche l'attivazione di prodotti online, deve essere usata solo per le installazioni con contratti multilicenza. In particolare, l'uso di questa preferenza impedirà Office applicazioni di accedere agli endpoint seguenti:
  
- ```https://odc.officeapps.live.com```
    
- ```https://*.firstpartyapps.oaspapps.com```
    
- Tutti gli endpoint elencati nella sezione "Accedi" precedente.
    
- Tutti gli endpoint elencati nella sezione "Ricerca intelligente" sopra riportata.
    
- Tutti gli endpoint elencati nella sezione "Attivazione del prodotto" sopra riportata.
    
- Tutti gli endpoint elencati nella sezione "App Office (aka componenti aggiuntivi)" sopra.
    
Per ristabilire la funzionalità completa per l'utente, imposta la preferenza su "2" o rimuovila.
  
> [!NOTE]
> Questa preferenza richiede Office per Mac build 15.25 [160726] o versione successiva. 
  
### <a name="telemetry"></a>Telemetria
  
Office per Mac invia le informazioni di telemetria a Microsoft a intervalli regolari. I dati vengono caricati nell'endpoint "Nexus". I dati di telemetria consentono al team di progettazione di valutare l'integrità e gli eventuali comportamenti imprevisti di ogni app Office. Esistono due categorie di telemetria:
  
- **Heartbeat** contiene informazioni sulla versione e sulla licenza. Questi dati vengono inviati immediatamente all'avvio dell'app. 
    
- **Usage** contiene informazioni sull'uso delle app e sugli errori non irreversibili. Questi dati vengono inviati ogni 60 minuti. 
    
Microsoft prende molto sul serio la privacy. Per informazioni sui criteri di raccolta dati di Microsoft, vedere [https://privacy.microsoft.com](https://privacy.microsoft.com) . Per impedire alle applicazioni di inviare telemetria "Usage", è possibile modificare la **preferenza SendAllTelemetryEnabled.** La preferenza è per applicazione e può essere impostata tramite profili di configurazione macOS o manualmente da Terminal: 
  
```defaults write com.microsoft.Word SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Excel SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Powerpoint SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Outlook SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.onenote.mac SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.autoupdate2 SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Office365ServiceV2 SendAllTelemetryEnabled -bool FALSE```

La telemetria heartbeat viene sempre inviata e non può essere disabilitata.
  
### <a name="crash-reporting"></a>Segnalazione arresti anomalo del sistema
  
Quando si verifica un errore irreversibile dell'applicazione, l'applicazione verrà interrotta in modo imprevisto e verrà caricata una segnalazione di arresto anomalo nel servizio "Watson". Il rapporto di arresto anomalo è costituito da uno stack di chiamate, ovvero l'elenco dei passaggi che l'applicazione stava elaborando prima dell'arresto anomalo. Questi passaggi consentono al team di progettazione di identificare la funzione esatta che ha avuto esito negativo e il motivo.
  
In alcuni casi, il contenuto di un documento causa l'arresto anomalo dell'applicazione. Se l'app identifica il documento come causa, chiederà all'utente se è possibile inviare anche il documento insieme al call-stack. Gli utenti possono fare una scelta informata a questa domanda. Gli amministratori IT possono avere requisiti rigorosi sulla trasmissione dei documenti e prendere la decisione per conto dell'utente di non inviare mai documenti. La preferenza seguente può essere impostata per impedire l'invio di documenti e per eliminare la richiesta all'utente:
  
```defaults write com.microsoft.errorreporting IsAttachFilesEnabled -bool FALSE```

> [!NOTE]
> Se **SendAllTelemetryEnabled** è impostato su **FALSE,** tutte le segnalazioni di arresto anomalo del processo sono disabilitate. Per abilitare la segnalazione di arresti anomalo del sistema senza inviare telemetria di utilizzo, è possibile impostare la preferenza seguente: ```defaults write com.microsoft.errorreporting IsMerpEnabled -bool TRUE``` 
  
### <a name="updates"></a>Aggiornamenti
  
Microsoft rilascia Office per Mac aggiornamenti a intervalli regolari (in genere una volta al mese). Incoraggiamo vivamente gli utenti e gli amministratori IT a mantenere aggiornati i computer per garantire l'installazione delle correzioni di sicurezza più recenti. Nei casi in cui gli amministratori IT desiderano controllare e gestire attentamente gli aggiornamenti dei computer, è possibile impostare la preferenza seguente per impedire al processo di aggiornamento automatico di rilevare e offrire automaticamente gli aggiornamenti dei prodotti:
  
```defaults write com.microsoft.autoupdate2 HowToCheck -string 'Manual'```

### <a name="blocking-requests-with-a-firewallproxy"></a>Blocco delle richieste con un firewall/proxy
  
Se l'organizzazione blocca le richieste agli URL tramite un firewall o un server proxy, assicurati di configurare gli URL elencati in questo documento come consentiti o quelli elencati con una risposta 40X (ad esempio, 403 o 404). Una risposta 40X consentirà alle applicazioni di Office di accettare normalmente l'impossibilità di accedere alla risorsa e offrirà un'esperienza utente più veloce rispetto alla semplice eliminazione della connessione, che a sua volta causerà un nuovo tentativo del client.
  
Se il server proxy richiede l'autenticazione, al client verrà restituita una risposta 407. Per un'esperienza ottimale, assicurarsi di utilizzare Office per Mac build 15.27 o successive, in quanto includono correzioni specifiche per l'utilizzo dei server NTLM e Kerberos.
  
  
## <a name="see-also"></a>Vedere anche

[URL e intervalli di indirizzi IP per Office 365](urls-and-ip-address-ranges.md)

