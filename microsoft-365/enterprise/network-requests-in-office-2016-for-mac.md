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
description: In questo articolo vengono descritti gli endpoint e gli URL di Office per le applicazioni Mac che tentano di raggiungere e i servizi forniti.
ms.openlocfilehash: b777b4ea7e03495cb6389be8fe05e96a26fd9664
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691269"
---
# <a name="network-requests-in-office-for-mac"></a>Richieste di rete in Office per Mac

Le applicazioni di Office per Mac forniscono un'esperienza di app nativa sulla piattaforma macOS. Ogni app è progettata per funzionare in diversi scenari, tra cui gli stati in cui non è disponibile alcun accesso alla rete. Quando un computer è connesso a una rete, le applicazioni si connettono automaticamente a una serie di servizi basati sul Web per fornire funzionalità avanzate. Nelle informazioni seguenti vengono descritti gli endpoint e gli URL che le applicazioni tentano di raggiungere e i servizi forniti. Queste informazioni sono utili per la risoluzione dei problemi relativi alla configurazione della rete e per l'impostazione di criteri per i server proxy di rete. I dettagli in questo articolo sono destinati a completare l' [articolo di Office 365 URL e degli intervalli di indirizzi](urls-and-ip-address-ranges.md), che include gli endpoint per i computer che eseguono Microsoft Windows. Se non specificato, le informazioni contenute in questo articolo si applicano anche a Office 2019 per Mac e Office 2016 per Mac, che sono disponibili come acquisto una tantum da un rivenditore o tramite un contratto multilicenza. 

  
La maggior parte di questo articolo è illustrata in dettaglio gli URL di rete, il tipo e la descrizione del servizio o della funzionalità forniti dall'endpoint. Ognuna delle app di Office può essere diversa nell'utilizzo del servizio e dell'endpoint. Nelle tabelle riportate di seguito vengono definite le app seguenti:
  
- W: parola
- P: PowerPoint
- X: Excel
- O: Outlook
- N: OneNote
   
Il tipo di URL è definito come indicato di seguito:
  
- ST: static-l'URL è hardcoded nell'applicazione client.
    
- SS: semi-static-l'URL è codificato come parte di una pagina Web o di un redirector.
    
- CS: config Service-l'URL viene restituito come parte del servizio di configurazione di Office.

    
## <a name="office-for-mac-default-configuration"></a>Configurazione predefinita di Office per Mac

 **Installazione e aggiornamenti**
  
I seguenti endpoint di rete vengono utilizzati per scaricare il programma di installazione di Office per Mac dalla rete di distribuzione dei contenuti (CDN) di Microsoft.
  
|**URL**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|```https://go.microsoft.com/fwlink/```  <br/> |ST  <br/> |Microsoft 365 Installation Portal forward link Service ai pacchetti di installazione più recenti.  <br/> |
|```https://officecdn-microsoft-com.akamaized.net/```  <br/> |SS  <br/> |Percorso dei pacchetti di installazione nella rete di distribuzione del contenuto.  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |SS  <br/> |Percorso dei pacchetti di installazione nella rete di distribuzione del contenuto.  <br/> |
|```https://officeci-mauservice.azurewebsites.net/```  <br/> |ST  <br/> |Endpoint di controllo di gestione per Microsoft AutoUpdate  <br/> |
   
 **Primo avvio delle app**
  
I seguenti endpoint di rete vengono contattati al primo avvio di un'app di Office. Tali endpoint offrono funzionalità di Office avanzate per gli utenti e gli URL vengono contattati indipendentemente dal tipo di licenza (incluse le installazioni con contratti multilicenza).
  
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://config.edge.skype.com/```  <br/> |WXPON  <br/> |ST  <br/> |Configurazione di ' Flight '-consente di leggere e sperimentare la funzionalità.  <br/> |
|```https://ocos-office365-s2s.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |Test di configurazione della rete ' flighting '  <br/> |
|```https://client-office365-tas.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |Test di configurazione della rete ' flighting '  <br/> |
|```https://officeclient.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Servizio di configurazione di Office-elenco master degli endpoint del servizio.  <br/> |
|```https://nexusrules.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Download di telemetria di Office Rules-informa il client sui dati e sugli eventi da caricare nel servizio di telemetria.  <br/> |
|```https://mobile.pipe.aria.microsoft.com/```  <br/> |N  <br/> |CS  <br/> |Servizio di telemetria di OneNote  <br/> |
|```https://nexus.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Reporting di caricamento di telemetria di Office-"Heartbeart" e gli eventi di errore che si verificano nel client vengono caricati nel servizio di telemetria.  <br/> |
|```https://templateservice.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Office Template Service-fornisce agli utenti modelli di documento online.  <br/> |
|```https://omextemplates.content.office.net/```  <br/> |WXP  <br/> |CS  <br/> |Download dei modelli di Office-archiviazione delle immagini del modello PNG.  <br/> |
|```https://store.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Configurazione di archiviazione per le app di Office.  <br/> |
|```https://odc.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Catalogo di Office Document Integration Services (elenco di servizi e endpoint) e individuazione dell'area di autenticazione domestica.  <br/> |
|```https://cdn.odc.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Risorse per l'individuazione dell'area di autenticazione domestica V2 (15,40 e versioni successive)  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Manifesti di Microsoft AutoUpdate: consente di controllare se sono disponibili aggiornamenti  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |WXPO  <br/> |SS  <br/> |Libreria JavaScript Microsoft AJAX  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |App Wikipedia per la configurazione e le risorse di Office.  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Applicazione di Bing Map per la configurazione e le risorse di Office.  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |App grafico utenti per la configurazione e le risorse di Office.  <br/> |
|```https://www.onenote.com/```  <br/> |N  <br/> |ST  <br/> |Novità relative al contenuto di OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |ST  <br/> |Nuovo contenuto per OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |SS  <br/> |Quali sono le nuove immagini di OneNote.  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |ST  <br/> |Servizio di supporto in-app.  <br/> |
|```https://prod-global-autodetect.acompli.net/```  <br/> |O  <br/> |ST  <br/> |Servizio di rilevamento degli account di posta elettronica.  <br/> |
|```https://autodiscover-s.outlook.com/```  <br/> |WXPO  <br/> |ST  <br/> |Individuazione automatica di Outlook  <br/> |
|```https://outlook.office365.com/```  <br/> |WXPO  <br/> |ST  <br/> |Endpoint di Outlook per il servizio Microsoft 365.  <br/> |
|```https://r1.res.office365.com/```  <br/> |O  <br/> |ST  <br/> |Icone per i componenti aggiuntivi di Outlook.  <br/> |
   
> [!NOTE]
> Il servizio di configurazione di Office funge da servizio di individuazione automatica per tutti i client di Microsoft Office, non solo per Mac. Gli endpoint restituiti nella risposta sono semistatici in quanto la modifica è molto rara, ma è comunque possibile. 
  
 **Accesso**
  
Quando si esegue l'accesso all'archiviazione basata sul cloud, vengono contattati i seguenti endpoint di rete. A seconda del tipo di account, è possibile contattare diversi servizi. Ad esempio:
  
- **MSA: account Microsoft** -utilizzato in genere per gli scenari consumer e retail 
    
- **OrgID: account dell'organizzazione** -utilizzato in genere per gli scenari commerciali 
    
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://login.windows.net/```  <br/> |WXPON  <br/> |ST  <br/> |Servizio di autorizzazione di Windows  <br/> |
|```https://login.microsoftonline.com/```  <br/> |WXPON  <br/> |ST  <br/> |Microsoft 365 login Service (OrgID)  <br/> |
|```https://login.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Servizio di accesso account Microsoft (MSA)  <br/> |
|```https://auth.gfx.ms/```  <br/> |WXPON  <br/> |CS  <br/> |Helper del servizio account di accesso Microsoft (MSA)  <br/> |
|```https://secure.aadcdn.microsoftonline-p.com/```  <br/> |WXPON  <br/> |SS  <br/> |Branding di login Microsoft 365 (OrgID)  <br/> |
|```https://ocws.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Localizzatore di archiviazione di documenti e posizioni  <br/> |
|```https://roaming.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Servizio documenti utilizzato più di recente (MRU)  <br/> |
   
> [!NOTE]
> Per le licenze basate su sottoscrizione e al dettaglio, la firma in entrambi attiva il prodotto e consente l'accesso a risorse cloud come OneDrive. Per le installazioni con contratti multilicenza, agli utenti viene ancora richiesto di eseguire l'accesso (per impostazione predefinita), ma questo è necessario solo per accedere alle risorse del cloud, in quanto il prodotto è già stato attivato. 
  
 **Attivazione del prodotto**
  
Gli endpoint di rete riportati di seguito si applicano a Microsoft 365 Subscription and Retail License Activations. In particolare, questa operazione non si applica alle installazioni con contratti multilicenza.
  
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://ols.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Servizio gestione licenze Office  <br/> |
   
 **Novità di contenuto**
  
Gli endpoint di rete riportati di seguito si applicano solo alla sottoscrizione Microsoft 365.
  
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://contentstorage.osi.office.net/```  <br/> |WXPO  <br/> |SS  <br/> |Che cos'è il nuovo contenuto della pagina JSON.  <br/> |
   
 **Strumento ricerche**
  
Gli endpoint di rete riportati di seguito si applicano solo alla sottoscrizione Microsoft 365.
  
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |Servizio Web del ricercatore  <br/> |
|```https://cdn.entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |Contenuto statico del ricercatore  <br/> |
|```https://www.bing.com/```  <br/> |W  <br/> |CS  <br/> |Provider di contenuto del ricercatore  <br/> |
   
 **Ricerca intelligente**
  
Gli endpoint di rete riportati di seguito si applicano sia alla sottoscrizione Microsoft 365 che alle attivazioni di contratti multilicenza e retail.
  
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://uci.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Servizio Web Insights  <br/> |
|```https://ajax.googleapis.com/```  <br/> |WXPN  <br/> |CS  <br/> |Raccolta JQuery  <br/> |
|```https://cdnjs.cloudflare.com/```  <br/> |WXPN  <br/> |CS  <br/> |Supporto della libreria JavaScript  <br/> |
|```https://www.bing.com/```  <br/> |WXPN  <br/> |CS  <br/> |Provider di contenuto Insights  <br/> |
|```https://tse1.mm.bing.net/```  <br/> |WXPN  <br/> |CS  <br/> |Provider di contenuto Insights  <br/> |
   
 **PowerPoint Designer**
  
Gli endpoint di rete riportati di seguito si applicano solo alla sottoscrizione Microsoft 365.
  
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://pptsgs.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |Servizio Web di PowerPoint designer  <br/> |
   
 **Avvio rapido di PowerPoint**
  
Gli endpoint di rete riportati di seguito si applicano solo alla sottoscrizione Microsoft 365.
  
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://pptcts.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |Servizio Web QuickStart di PowerPoint  <br/> |
   
 **Inviare un sorriso/cipiglio**
  
Gli endpoint di rete riportati di seguito si applicano sia alla sottoscrizione Microsoft 365 che alle attivazioni di contratti multilicenza e retail.
  
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://sas.office.microsoft.com/```  <br/> |WXPON  <br/> |CS  <br/> |Inviare un servizio Smile  <br/> |
   
 **Supporto per i contatti**
  
Gli endpoint di rete riportati di seguito si applicano sia alla sottoscrizione Microsoft 365 che alle attivazioni di contratti multilicenza e retail.
  
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://powerlift-frontdesk.acompli.net/```  <br/> |O  <br/> |CS  <br/> |Contattare il servizio supporto tecnico  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |CS  <br/> |Servizio di supporto in-app  <br/> |
   
 **Salva come PDF**
  
Gli endpoint di rete riportati di seguito si applicano sia alla sottoscrizione Microsoft 365 che alle attivazioni di contratti multilicenza e retail.
  
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://wordcs.officeapps.live.com/```  <br/> |W  <br/> |CS  <br/> |Servizio di conversione documenti di Word (PDF)  <br/> |
   
 **App di Office (componenti aggiuntivi aka)**
  
Quando i componenti aggiuntivi di Office app sono considerati attendibili, gli endpoint di rete seguenti si applicano sia alla sottoscrizione Microsoft 365 che alle attivazioni di contratti multilicenza o al dettaglio.
  
|**URL**|**App**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|```https://store.office.com/```  <br/> |WXPO  <br/> |CS  <br/> |Configurazione di Office App Store  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |Risorse per le app di Wikipedia  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Bing Map risorse delle app  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com```  <br/> |X  <br/> |SS  <br/> |Risorse delle app del grafico utenti  <br/> |
|```https://o15.officeredir.microsoft.com/```  <br/> |WPX  <br/> |SS  <br/> |Servizio di reindirizzamento di Office  <br/> |
|```https://appsforoffice.microsoft.com/```  <br/> |WXP  <br/> |SS  <br/> |Librerie JavaScript di Office  <br/> |
|```https://telemetry.firstpartyapps.oaspapps.com/```  <br/> |WX  <br/> |SS  <br/> |Servizio di telemetria e Reporting per le app di Office  <br/> |
|```https://ajax.microsoft.com/```  <br/> |W  <br/> |SS  <br/> |Libreria JavaScript Microsoft AJAX  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |X  <br/> |SS  <br/> |Libreria JavaScript Microsoft AJAX  <br/> |
|```https://c.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Librerie JavaScript di Office  <br/> |
|```https://c1.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Risorse di supporto  <br/> |
|```https://cs.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Risorse di supporto  <br/> |
|```https://c.bing.com/```  <br/> |WPXO  <br/> |SS  <br/> |Risorse di supporto  <br/> |
|```https://*.cdn.optimizely.com/```  <br/> |WPXO  <br/> |SS  <br/> |Libreria JavaScript  <br/> |
|```https://errors.client.optimizely.com/```  <br/> |WPX  <br/> |SS  <br/> |Segnalazione degli errori  <br/> |
|```https://*-contentstorage.osi.office.net/```  <br/> |WPXO  <br/> |SS  <br/> |Risorse per i tipi di carattere  <br/> |
|```https://nexus.ensighten.com/```  <br/> |WPXO  <br/> |SS  <br/> |Servizio di telemetria  <br/> |
|```https://browser.pipe.aria.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Report di telemetria  <br/> |
|```https://*.vo.msecnd.net/```  <br/> |WPXO  <br/> |SS  <br/> |Raccolta di risorse di Microsoft Store  <br/> |
|```https://*.wikipedia.org/```  <br/> |W  <br/> |SS  <br/> |Risorse della pagina di Wikipedia  <br/> |
|```https://upload.wikimedia.org/```  <br/> |W  <br/> |SS  <br/> |Risorse multimediali Wikipedia  <br/> |
|```https://wikipedia.firstpartyappssandbox.oappseperate.com/```  <br/> |W  <br/> |SS  <br/> |Struttura sandbox di Wikipedia  <br/> |
|```https://*.virtualearth.net/```  <br/> |X  <br/> |SS  <br/> |Modelli di mappa  <br/> |
   
 **Collegamenti sicuri**
  
L'endpoint di rete seguente si applica solo a tutte le applicazioni di Office per la sottoscrizione di Microsoft 365.
  
|**URL**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|```https://*.oscs.protection.outlook.com/```  <br/> |CS  <br/> |Servizio Microsoft Safe link  <br/> |
   
 **Segnalazione crash**
  
L'endpoint di rete seguente si applica a tutte le applicazioni di Office sia per la sottoscrizione Microsoft 365 che per le attivazioni delle licenze di retail/volume. Quando un processo si blocca in modo imprevisto, viene generato un report e inviato al servizio Watson.
  
|**URL**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|```https://watson.microsoft.com/```  <br/> |ST  <br/> |Microsoft Error Reporting Service  <br/> |
|```https://officeci.azurewebsites.net/```  <br/> |ST  <br/> |Servizio Office collaborative Insights  <br/> |
   
## <a name="options-for-reducing-network-requests-and-traffic"></a>Opzioni per la riduzione delle richieste di rete e del traffico

La configurazione predefinita di Office per Mac offre la migliore esperienza utente, sia in termini di funzionalità che di conservazione del computer aggiornato. In alcuni scenari è possibile che si desideri impedire alle applicazioni di contattare gli endpoint di rete. In questa sezione vengono illustrate le opzioni per farlo.
  
 ### <a name="disabling-cloud-sign-in-and-office-add-ins"></a>Disabilitazione dell'accesso al cloud e ai componenti aggiuntivi di Office
  
Contratti multilicenza i clienti possono avere criteri rigorosi per il salvataggio di documenti nell'archiviazione basata su cloud. Per disabilitare l'accesso a MSA/OrgID e accedere ai componenti aggiuntivi di Office, è possibile impostare le seguenti preferenze per applicazione.
  
- ```defaults write com.microsoft.Word UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Excel UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Powerpoint UseOnlineContent -integer 0```

Se gli utenti tentano di accedere alla funzione di accesso, visualizzeranno un errore che non è presente in una connessione di rete. Poiché questa preferenza blocca anche l'attivazione del prodotto online, è consigliabile utilizzarla solo per le installazioni con contratti multilicenza. In particolare, l'utilizzo di questa preferenza impedirà alle applicazioni di Office di accedere ai seguenti endpoint:
  
- ```https://odc.officeapps.live.com```
    
- ```https://*.firstpartyapps.oaspapps.com```
    
- Tutti gli endpoint elencati nella sezione ' accedi ' sopra.
    
- Tutti gli endpoint elencati nella sezione ' ricerca intelligente ' precedente.
    
- Tutti gli endpoint elencati nella sezione ' attivazione del prodotto ' precedente.
    
- Tutti gli endpoint elencati nella sezione ' Office Apps (aka Add-ins)' sopra.
    
Per ristabilire la funzionalità completa per l'utente, impostare la preferenza su' 2' oppure rimuoverla.
  
> [!NOTE]
> Questa preferenza richiede Office per Mac Build 15,25 [160726] o versione successiva. 
  
### <a name="telemetry"></a>Telemetria
  
Office per Mac invia nuovamente a Microsoft le informazioni di telemetria a intervalli regolari. I dati vengono caricati nell'endpoint ' Nexus '. I dati di telemetria aiutano il team di ingegneri a valutare l'integrità e gli eventuali comportamenti imprevisti di ogni app di Office. Sono disponibili due categorie di telemetria:
  
- **Heartbeat** contiene informazioni sulla versione e sulla licenza. Questi dati vengono inviati subito dopo l'avvio delle app. 
    
- **Usage** contiene informazioni sul modo in cui vengono utilizzate le app e gli errori non irreversibili. Questi dati vengono inviati ogni 60 minuti. 
    
Microsoft prende molto sul serio la propria privacy. È possibile leggere informazioni sui criteri di raccolta dati di Microsoft all'indirizzo [https://privacy.microsoft.com](https://privacy.microsoft.com) . Per impedire alle applicazioni di inviare la telemetria "Usage", è possibile regolare la preferenza **SendAllTelemetryEnabled** . La preferenza è per applicazione e può essere impostata tramite i profili di configurazione di macOS o manualmente da terminale: 
  
```defaults write com.microsoft.Word SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Excel SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Powerpoint SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Outlook SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.onenote.mac SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.autoupdate2 SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Office365ServiceV2 SendAllTelemetryEnabled -bool FALSE```

La telemetria del battito cardiaco viene sempre inviata e non può essere disabilitata.
  
### <a name="crash-reporting"></a>Segnalazione crash
  
Quando si verifica un errore irreversibile dell'applicazione, l'applicazione inaspettatamente termina e carica un rapporto di arresto anomalo nel servizio ' Watson '. Il rapporto crash è costituito da uno stack di chiamate, che è l'elenco dei passaggi che l'applicazione stava elaborando fino all'arresto anomalo. Questi passaggi consentono al team di progettazione di identificare la funzione esatta che ha avuto esito negativo e perché.
  
In alcuni casi, il contenuto di un documento provocherà un arresto anomalo dell'applicazione. Se l'app identifica il documento come causa, verrà chiesto all'utente se va bene anche inviare il documento insieme allo stack di chiamate. Gli utenti possono prendere una decisione informata su questa domanda. Gli amministratori IT possono avere requisiti rigorosi per la trasmissione dei documenti e prendere la decisione per conto dell'utente di non inviare mai documenti. È possibile impostare la preferenza seguente per impedire l'invio di documenti e per sopprimere la richiesta all'utente:
  
```defaults write com.microsoft.errorreporting IsAttachFilesEnabled -bool FALSE```

> [!NOTE]
> Se **SendAllTelemetryEnabled** è impostato su **false**, tutte le segnalazioni di crash per tale processo sono disattivate. Per abilitare la segnalazione degli arresti anomali senza inviare la telemetria di utilizzo, è possibile impostare la preferenza seguente: ```defaults write com.microsoft.errorreporting IsMerpEnabled -bool TRUE``` 
  
### <a name="updates"></a>Aggiornamenti
  
Microsoft rilascia gli aggiornamenti di Office per Mac a intervalli regolari (in genere una volta al mese). È consigliabile incoraggiare gli utenti e gli amministratori IT a mantenere aggiornate le macchine per assicurarsi che siano installate le ultime correzioni di sicurezza. Nei casi in cui gli amministratori IT desiderano controllare e gestire gli aggiornamenti del computer, è possibile impostare la preferenza seguente per evitare che il processo di aggiornamento automatico rilevi e offra gli aggiornamenti del prodotto:
  
```defaults write com.microsoft.autoupdate2 HowToCheck -string 'Manual'```

### <a name="blocking-requests-with-a-firewallproxy"></a>Blocco delle richieste con un firewall/proxy
  
Se l'organizzazione blocca le richieste agli URL tramite un firewall o un server proxy, assicurarsi di configurare gli URL elencati in questo documento come ammessi oppure bloccarli nell'elenco con una risposta 40X (ad esempio, 403 o 404). Una risposta 40X consentirà alle applicazioni di Office di accettare con garbo l'impossibilità di accedere alla risorsa e fornirà un'esperienza utente più rapida, oltre alla semplice eliminazione della connessione, che a sua inattività farà sì che il client ritenti.
  
Se il server proxy richiede l'autenticazione, verrà restituita una risposta 407 al client. Per un'esperienza ottimale, assicurarsi di utilizzare Office per Mac Builds 15,27 o versioni successive, poiché includono correzioni specifiche per l'utilizzo dei server NTLM e Kerberos.
  
  
## <a name="see-also"></a>Vedere anche

[URL e intervalli di indirizzi IP per Office 365](urls-and-ip-address-ranges.md)

