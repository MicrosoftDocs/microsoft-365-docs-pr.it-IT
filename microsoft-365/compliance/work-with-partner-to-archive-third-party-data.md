---
title: Collaborare con un partner per archiviare i dati di terze parti
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come configurare un connettore personalizzato per importare dati di terze parti da origini dati come Salesforce Chatter, Yahoo Messenger o Yammer.
ms.openlocfilehash: 64e903604ea56e5f53e3cc154bd54459a6d8d554
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620212"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a>Collaborare con un partner per archiviare i dati di terze parti

È possibile collaborare con un partner Microsoft per importare e archiviare dati da un'origine dati di terze parti in Microsoft 365. Un partner può fornire un connettore personalizzato configurato per estrarre gli elementi dall'origine dati di terze parti (su base regolare) e quindi importare tali elementi. Il connettore partner converte il contenuto di un elemento dall'origine dati in un formato di messaggio di posta elettronica e quindi archivia gli elementi nelle cassette postali. Dopo l'importazione dei dati di terze parti, è possibile applicare a questi dati le funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, eDiscovery, archiviazione In-Place, controllo e criteri di conservazione di Microsoft 365.

>[!IMPORTANT]
>La [soluzione di conformità](communication-compliance.md) delle comunicazioni in Microsoft 365 non può essere applicata ai dati di terze parti importati dai connettori partner menzionati in questo articolo. 

Ecco una panoramica del processo e dei passaggi necessari per collaborare con un partner Microsoft per importare dati di terze parti.

[Step 1: Find a third-party data partner](#step-1-find-a-third-party-data-partner)

[Passaggio 2: Creare e configurare una cassetta postale di dati di terze parti](#step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365)

[Step 3: Configure user mailboxes for third-party data](#step-3-configure-user-mailboxes-for-third-party-data)

[Passaggio 4: fornire informazioni al partner](#step-4-provide-your-partner-with-information)

[Passaggio 5: Registrare il connettore dati di terze parti in Azure Active Directory](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>Funzionamento del processo di importazione dei dati di terze parti

La figura e la descrizione seguenti illustrano il funzionamento del processo di importazione dei dati di terze parti quando si collabora con un partner.
  
![Funzionamento del processo di importazione dei dati di terze parti](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. Il cliente collabora con il partner scelto per configurare un connettore che estrarrà gli elementi dall'origine dati di terze parti e quindi importerà tali elementi in Microsoft 365.
    
2. Il connettore partner si connette a origini dati di terze parti tramite un'API di terze parti (su base pianificata o configurata) ed estrae gli elementi dall'origine dati. Il connettore partner converte il contenuto di un elemento in un formato di messaggio di posta elettronica. Per una [descrizione](#more-information) dello schema in formato messaggio, vedere la sezione Ulteriori informazioni. 
    
3. Il connettore partner si connette al servizio Azure in Microsoft 365 utilizzando il servizio Web Exchange (EWS) tramite un punto finale noto.
    
4. Gli elementi vengono importati nella cassetta postale di un utente specifico oppure in una cassetta postale generale di dati di terze parti. Il fatto che un elemento sia importato nella cassetta postale di un utente specifico o nella cassetta postale di dati di terze parti dipende dai seguenti criteri:
    
   1. **Elementi con un ID utente corrispondente a un account utente:** Se il connettore partner può mappare l'ID utente dell'elemento nell'origine dati di terze parti a  un ID utente specifico in Microsoft 365, l'elemento viene copiato nella cartella Ripuliture nella cartella Elementi ripristinabili dell'utente. Gli utenti non possono accedere agli elementi nella cartella Ripuliture. Tuttavia, è possibile utilizzare gli strumenti di eDiscovery per cercare gli elementi nella cartella Ripuliture.
    
   1. **Elementi che non dispongono di un ID utente corrispondente a un account utente:** Se il connettore partner non è in grado di mappare l'ID  utente di un elemento a un ID utente specifico, l'elemento viene copiato nella cartella Posta in arrivo della cassetta postale di dati di terze parti. L'importazione di elementi nella posta in arrivo consente a un utente dell'organizzazione di accedere alla cassetta postale di terze parti per visualizzare e gestire questi elementi e vedere se è necessario prevedere modifiche nella configurazione del connettore partner.
 
## <a name="step-1-find-a-third-party-data-partner"></a>Passaggio 1: trovare un partner di dati di terze parti

Un componente chiave per l'archiviazione di dati di terze parti in Microsoft 365 è la ricerca e la collaborazione con un partner Microsoft specializzato nell'acquisizione di dati da un'origine dati di terze parti e nell'importazione in Microsoft 365. Dopo l'importazione, i dati possono essere archiviati e conservati insieme agli altri dati Microsoft dell'organizzazione, ad esempio la posta elettronica da Exchange e i documenti da SharePoint e OneDrive for Business. Un partner crea un connettore che estrae i dati dalle origini dati di terze parti dell'organizzazione (ad esempio BlackBerry, Facebook, Google+, Thomson Reuters, Twitter e YouTube) e li passa a un'API di Microsoft 365 che importa gli elementi nelle cassette postali di Exchange come messaggi di posta elettronica.
  
Nelle sezioni seguenti sono elencati i partner Microsoft (e le origini dati di terze parti supportate) che partecipano al programma per l'archiviazione dei dati di terze parti in Microsoft 365.

[17a-4 LLC](#17a-4-llc)
  
[ArchiveSocial](#archivesocial)
  
[Globanet](#globanet)
  
[OpenText](#opentext)
  
[Smarsh](#smarsh)

[Verba](#verba)
  
### <a name="17a-4-llc"></a>17a-4 LLC

[17a-4 LLC](https://www.17a-4.com) supporta le origini dati di terze parti seguenti:
  
- BlackBerry
    
- Flussi di dati di Bloomberg
    
- Cisco Jabber
    
- FactSet
    
- HipChat
    
- InvestEdge
    
- LivePerson
    
- Flussi di dati MessageLabs
    
- OpenText
    
- Guida "click-to-call" di Oracle/ATG
    
- Pivot IMTRADER
    
- Microsoft SharePoint
    
- MindAlign
    
- Sitrion One (Newsgator)
    
- Skype for Business (Lync/OCS)
    
- Skype for Business Online (Lync Online)
    
- Database SQL
    
- Squawker
    
- Thomson Reuters Eikon Messenger
  

  
### <a name="archivesocial"></a>ArchiveSocial

[ArchiveSocial ](https://www.archivesocial.com) supporta le origini dati di terze parti seguenti: 
  
- Facebook
    
- Flickr
    
- Instagram
    
- LinkedIn
    
- Pinterest
    
- Twitter
    
- YouTube
    
- Vimeo
  
### <a name="globanet"></a>Globanet

[Globanet](https://www.globanet.com) supporta le origini dati di terze parti seguenti: 
  
- AOL con Pivot Client  
    
- Registri chiamate BlackBerry (v5, v10, v12)
    
- Messenger BlackBerry (v5, v10, v12)
    
- PIN BlackBerry (v5, v10, v12)
    
- SMS BlackBerry (v5, v10, v12)
    
- Chat Bloomber
    
- Posta Bloomberg
    
- Box
    
- CipherCloud per Salesforce Chatter
    
- Server presenza messaggistica istantanea Cisco &amp; (v10, v10.5.1 SU1, v11.0, v11.5 SU2)

- Cisco Webex Teams

- Citrix Workspace &amp; ShareFile

- CrowdCompass

- File di testo delimitati da personalizzati
    
- File XML personalizzati
    
- Facebook (Pagine)
    
- Factset
    
- FXConnect
    
- ICE Chat/YellowJacket
    
- Jive
    
- XIP Macgregor

- Microsoft Exchange Server
    
- Microsoft OneDrive for Business

- Microsoft Teams
       
- Microsoft Yammer
    
- Mobile Guard
    
- Pivot
    
- Salesforce Chatter

- Skype for Business Online
    
- Skype for Business, versioni 2007 R2 - 2016 (locale)
    
- Slack Enterprise Grid
    
- Symphony
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- Thomson Reuters Dealings 3000/FX Trading
    
- Twitter
    
- Chat UBS
    
- YouTube
  
### <a name="opentext"></a>OpenText

[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supporta le origini dati di terze parti seguenti: 
  
- Axs Encrypted
    
- Axs Exchange
    
- Axs Local Archive
    
- Axs PlaceHolder
    
- Axs Signed
    
- Bloomberg
    
- Thomson Reuters
  
### <a name="smarsh"></a>Smarsh

[Smarsh](https://www.smarsh.com) supporta le origini dati di terze parti seguenti: 
  
- AIM
    
- American Idol
    
- Apple Juice
    
- AOL con client Pivot
    
- Ares
    
- Bazaar Voice
    
- Bear Share
    
- Bit Torrent
    
- Registri chiamate BlackBerry (v5, v10, v12)
    
- Messenger BlackBerry (v5, v10, v12)
    
- PIN BlackBerry (v5, v10, v12)
    
- SMS BlackBerry (v5, v10, v12)
    
- Posta Bloomberg
    
- CellTrust
    
- Chat Import
    
- Chat Real Time Logging and Policy
    
- Chatter
    
- Server presenza messaggistica istantanea Cisco &amp; (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)
    
- Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)
    
- Importazione collaborazione
    
- Registrazione di collaborazione in tempo reale
    
- Connessione diretta
    
- Facebook
    
- FactSet
    
- FastTrack
    
- Gnutella
    
- Google+
    
- GoToMyPC
    
- Hopster
    
- HubConnex
    
- IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)
    
- IBM Connections Chat Cloud
    
- IBM Connections Social Cloud
    
- IBM SameTime Advanced 8.5.2 IFR1
    
- IBM SameTime Communicate 9.0
    
- IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)
    
- IBM SameTime Complete 9.0
    
- IBM SameTime Conference 9.0
    
- IBM SameTime Meeting 8.5.2 IFR1
    
- ICE/YellowJacket
    
- IM Import
    
- IM Real Time Logging and Policy
    
- Indii Messenger
    
- Instant Bloomberg
    
- IRC
    
- Jive
    
- Jive 6 Real Time Logging (v6, v7)
    
- Jive Import
    
- JXTA
    
- LinkedIn
    
- Microsoft Lync (2010, 2013)
    
- MFTP
    
- Microsoft Lync 2013 Voice
    
- Microsoft SharePoint (2010, 2013)
    
- Microsoft SharePoint Online
    
- Microsoft UC (Unified Communications)
    
- MindAlign
    
- Mobile Guard
    
- MSN
    
- My Space
    
- NEONetwork
    
- Microsoft 365 Lync dedicato
    
- Messaggistica istantanea condivisa di Microsoft 365
    
- Pinterest
    
- Pivot
    
- QQ
    
- Skype for Business 2015
    
- SoftEther
    
- Symphony
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- Tor
    
- TTT
    
- Twitter
    
- WinMX
    
- Winny
    
- Yahoo
    
- Yammer
    
- YouTube
    

### <a name="verba"></a>Verba

[Verba](https://www.verba.com) supporta le origini dati di terze parti seguenti: 
  
- Avaya Aura Video
    
- Avaya Aura Voice
    
- Avtec Radio
    
- Bosch/Telex Radio
    
- BroadSoft Video
    
- BroadSoft Voice
    
- Centile Voice
    
- Messaggistica immediata Cisco Jabber
    
- Cisco UC Video
    
- Cisco UC Voice
    
- Cisco UCCX/UCCE Video
    
- Cisco UCCX/UCCE Voice
    
- ESChat Radio
    
- Geoman Contact Expert
    
- IP Trade Voice
    
- Luware LUCS Contact Center
    
- Microsoft UC (Unified Communications)
    
- Mitel MiContact Center per Lync (prairieFyre)
    
- Oracle / Acme Packet Session Border Controller Video
    
- Oracle / Acme Packet Session Border Controller Voice
    
- Singtel Mobile Voice
    
- SIPREC Video
    
-  SIPREC Voice 
    
- Messaggistica immediata Skype for Business / Lync
    
- Video Skype for Business / Lync
    
- Chiamate Skype for Business / Lync
    
- Speakerbus Voice
    
- Video SIP/H.323 standard
    
- Chiamate SIP/H.323 standard
    
- Truphone Voice
    
- TwistedPair Radio
    
- Schermata di Computer Desktop di Windows
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365"></a>Passaggio 2: Creare e configurare una cassetta postale di dati di terze parti in Microsoft 365

Ecco i passaggi per la creazione e la configurazione di una cassetta postale di dati di terze parti per l'importazione di dati in Microsoft 365. Come spiegato in precedenza, gli elementi vengono importati in questa cassetta postale se il connettore partner non è in grado di mappare l'ID utente dell'elemento a un account utente.
  
 **Completare queste attività nell'interfaccia di amministrazione di Microsoft 365**
  
1. Creare un account utente e assegnare una licenza di Exchange Online Piano 2; vedere [Aggiungere utenti a Microsoft 365.](https://go.microsoft.com/fwlink/p/?LinkId=692098) È necessaria una licenza di Piano 2 per attivare il blocco per controversia legale per la cassetta postale o abilitare una cassetta postale di archiviazione con una quota di archiviazione illimitata.
    
2. Aggiungere l'account utente per la cassetta postale di dati di terze parti al ruolo di amministratore di **Exchange** in Microsoft 365; vedere [Assegnare ruoli di amministratore in Microsoft 365.](https://go.microsoft.com/fwlink/p/?LinkId=532393)
    
    > [!TIP]
    > Annotare le credenziali per l'account utente. È necessario fornirle al partner, come descritto nel passaggio 4. 
  
 **Completare queste attività nell'interfaccia di amministrazione di Exchange**
  
1. Nascondere la cassetta postale dei dati di terze parti dalla rubrica e da altri elenchi di indirizzi dell'organizzazione; vedere [Gestire le cassette postali degli utenti.](https://go.microsoft.com/fwlink/p/?LinkId=616058) In alternativa, è possibile eseguire il comando di PowerShell seguente:
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. Assegnare **l'autorizzazione FullAccess** alla cassetta postale dei dati di terze parti in modo che gli amministratori o i responsabili della conformità possano aprire la cassetta postale dei dati di terze parti nel client desktop di Outlook; vedere [Gestire le autorizzazioni per i destinatari.](https://go.microsoft.com/fwlink/p/?LinkId=692104)
    
3. Abilitare le seguenti funzionalità correlate alla conformità per la cassetta postale dei dati di terze parti:
    
    - Abilitare la cassetta postale di archiviazione; vedere [Abilitare le cassette postali di archiviazione](enable-archive-mailboxes.md) e Abilitare [l'archiviazione illimitata.](enable-unlimited-archiving.md) Ciò consente di liberare spazio di archiviazione nella cassetta postale principale configurando un criterio di archiviazione che sposta gli elementi di dati di terze parti nella cassetta postale di archiviazione. Ciò offre spazio di archiviazione illimitato per i dati di terze parti.
    
    - Abilitare il blocco per controversia legale nella cassetta postale di dati di terze parti. È inoltre possibile applicare un criterio di conservazione di Microsoft 365 nel Centro sicurezza e conformità. L'archiviazione di questa cassetta postale mantiene gli elementi di dati di terze parti (a tempo indeterminato o per una durata specificata) e ne impedisce l'eliminazione dalla cassetta postale. Vedere uno degli argomenti seguenti:
    
      - [Applicare un blocco per controversia legale a una cassetta postale](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [Informazioni sui criteri e sulle etichette di conservazione](retention.md)
    
    - Abilitare la registrazione di controllo delle cassette postali per l'accesso proprietario, delegato e amministratore alla cassetta postale dei dati di terze parti; vedere [Enable mailbox auditing](enable-mailbox-auditing.md). In questo modo è possibile controllare tutte le attività eseguite da qualsiasi utente che abbia accesso alla cassetta postale dei dati di terze parti.

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>Passaggio 3: configurare cassette postali degli utenti per i dati di terze parti

Il passaggio successivo consiste nel configurare cassette postali degli utenti per supportare i dati di terze parti. Completare queste attività utilizzando l'interfaccia di amministrazione di Exchange o utilizzando i cmdlet di Windows PowerShell corrispondenti.
  
1. Abilitare la cassetta postale di archiviazione per ogni utente; vedere [Abilitare le cassette postali di archiviazione](enable-archive-mailboxes.md) e Abilitare [l'archiviazione illimitata.](enable-unlimited-archiving.md)
    
2. Applicare un criterio di conservazione di Microsoft 365 alle cassette postali degli utenti in Conservazione per controversia legale; vedere uno degli argomenti seguenti: 
    
    - [Applicare un blocco per controversia legale a una cassetta postale](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [Informazioni sui criteri e sulle etichette di conservazione](retention.md)
    
    Come precedentemente illustrato, quando si abilita un blocco delle cassette postali, è possibile impostare una durata per definire quanto tempo devono essere conservati gli elementi dell'origine dati di terze parti oppure è possibile scegliere di conservare gli elementi per un periodo di tempo indeterminato.

## <a name="step-4-provide-your-partner-with-information"></a>Passaggio 4: fornire informazioni al partner

Il passaggio finale consiste nel fornire al partner le informazioni seguenti in modo che possano configurare il connettore per la connessione all'organizzazione per importare i dati nelle cassette postali degli utenti e nella cassetta postale di dati di terze parti. 
  
- L'endpoint usato per connettersi al servizio Azure in Microsoft 365:

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- Le credenziali di accesso (ID utente e password di Microsoft 365) della cassetta postale di dati di terze parti creata nel passaggio 2. Queste credenziali sono necessarie in modo che il connettore partner possa accedere e importare elementi nelle cassette postali degli utenti e nella cassetta postale dei dati di terze parti.
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>Passaggio 5: Registrare il connettore dati di terze parti in Azure Active Directory

A partire dal 30 settembre 2018, il servizio Azure in Microsoft 365 inizierà a usare l'autenticazione moderna in Exchange Online per autenticare i connettori di dati di terze parti che tentano di connettersi all'organizzazione per importare i dati. Il motivo di questa modifica è che l'autenticazione moderna garantisce una maggiore sicurezza rispetto al metodo corrente, basato su un elenco consenti per i connettori di terze parti che utilizzano l'endpoint descritto in precedenza per connettersi al servizio Azure.

Per consentire a un connettore di dati di terze parti di connettersi a Microsoft 365 utilizzando il nuovo metodo di autenticazione moderno, un amministratore dell'organizzazione deve acconsentire alla registrazione del connettore come applicazione di servizio attendibile in Azure Active Directory. Questa operazione viene eseguita accettando una richiesta di autorizzazione per consentire al connettore di accedere ai dati dell'organizzazione in Azure Active Directory. Dopo aver accettato questa richiesta, il connettore di dati di terze parti viene aggiunto come applicazione aziendale ad Azure Active Directory e rappresentato come entità servizio. Per ulteriori informazioni sul processo di consenso, vedere [Tenant Admin Consent.](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent)

Ecco i passaggi per accedere e accettare la richiesta di registrazione del connettore:

1. Passare a [questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e accedere utilizzando le credenziali di un amministratore globale.

   Verrà visualizzata la finestra di dialogo seguente. È possibile espandere i caret per esaminare le autorizzazioni che verranno assegnate al connettore.

   ![Viene visualizzata la finestra di dialogo per la richiesta delle autorizzazioni](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. Fare clic su **Accetta**.

Dopo aver accettato la richiesta, viene visualizzato il portale di [Azure.](https://portal.azure.com) Per visualizzare l'elenco delle applicazioni per l'organizzazione, fare clic su **Applicazioni Azure Active Directory**  >  **Enterprise.** Il connettore dati di terze parti di Microsoft 365 è elencato nel pannello **Applicazioni** aziendali.

> [!IMPORTANT]
> Dopo il 30 settembre 2018, i dati di terze parti non verranno più importati nelle cassette postali dell'organizzazione se non si registra un connettore di dati di terze parti in Azure Active Directory. Tenere presente che i connettori di dati di terze parti esistenti (quelli creati prima del 30 settembre 2018) devono essere registrati anche in Azure Active Directory seguendo la procedura descritta nel passaggio 5.

### <a name="revoking-consent-for-a-third-party-data-connector"></a>Revoca del consenso per un connettore dati di terze parti

Dopo che l'organizzazione acconsente alla richiesta di autorizzazione per registrare un connettore di dati di terze parti in Azure Active Directory, l'organizzazione può revocare tale consenso in qualsiasi momento. Tuttavia, revocando il consenso per un connettore, i dati dell'origine dati di terze parti non verranno più importati in Microsoft 365.

Per revocare il consenso per un connettore di dati di terze parti, è possibile eliminare l'applicazione (eliminando l'entità servizio corrispondente) da Azure Active Directory usando il pannello **Applicazioni enterprise** nel portale di Azure o [tramite Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) in PowerShell di Microsoft 365. È inoltre possibile utilizzare il cmdlet [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) in Azure Active Directory PowerShell.
  
## <a name="more-information"></a>Altre informazioni

- Come illustrato in precedenza, gli elementi provenienti da origini dati di terze parti vengono importati nelle cassette postali di Exchange come messaggi di posta elettronica. Il connettore partner importa l'elemento usando uno schema richiesto dall'API di Microsoft 365. Nella tabella seguente vengono descritte le proprietà del messaggio di un elemento di un'origine dati di terze parti dopo che è stato importato in una cassetta postale di Exchange come messaggio di posta elettronica. Nella tabella viene indicato anche se la proprietà del messaggio è obbligatoria. È necessario popolare le proprietà obbligatorie. Se un elemento non contiene una proprietà obbligatoria, non verrà importato in Microsoft 365. Il processo di importazione restituisce un messaggio di errore che spiega perché un elemento non è stato importato e quale proprietà è mancante.<br/><br/>
    
    |**Proprietà del messaggio**|**Obbligatorio?**|**Descrizione**|**Valore di esempio**|
    |:-----|:-----|:-----|:-----|
    |**Da** <br/> |Sì  <br/> |L'utente che ha originariamente creato o inviato l'elemento nell'origine dati di terze parti. Il connettore partner tenta di mappare l'ID utente dall'elemento di origine (ad esempio un handle twitter) a un account utente per tutti i partecipanti (utenti nei campi FROM e TO). Verrà importata una copia del messaggio nella cassetta postale di ogni partecipante. Se nessuno dei partecipanti dell'elemento può essere mappato a un account utente, l'elemento verrà importato nella cassetta postale di archiviazione di terze parti in Microsoft 365.  <br/> <br/> Il partecipante identificato come mittente dell'elemento deve disporre di una cassetta postale attiva nell'organizzazione in cui viene importato l'elemento. In caso contrario, viene restituito l'errore seguente:<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**A** <br/> |Sì  <br/> |L'utente che ha ricevuto un elemento, se applicabile per un elemento nell'origine dati.  <br/> | `bob@contoso.com` <br/> |
    |**Oggetto** <br/> |No  <br/> |L'oggetto dell'elemento di origine.  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**DATE** <br/> |Sì  <br/> |Data in cui l'elemento è stato originariamente creato o pubblicato nell'origine dati del cliente. Ad esempio, la data in cui un messaggio di Twitter è stato tingato.  <br/> | `01 NOV 2015` <br/> |
    |**BODY** <br/> |No  <br/> |Il contenuto del messaggio o del post. Per alcune origini dati, il contenuto di questa proprietà può corrispondere al contenuto della proprietà **SUBJECT**. Durante il processo di importazione, il connettore partner tenta di mantenere la massima fedeltà possibile dall'origine di contenuto. Se possibile, i file, gli elementi grafici o altri contenuti del corpo dell'elemento di origine sono inclusi in questa proprietà. In caso contrario, il contenuto dell'elemento di origine è incluso nella proprietà **ATTACHMENT**. Il contenuto di questa proprietà dipende dal connettore partner e dalla capacità della piattaforma di origine.  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**ATTACHMENT** <br/> |No  <br/> |Se un elemento nell'origine dati (ad esempio un tweet su Twitter o una conversazione di messaggistica istantanea) contiene un file allegato o include immagini, la connessione partner tenterà innanzitutto di includere allegati nella proprietà **BODY.** Se non è possibile, viene aggiunto alla proprietà ** ATTACHMENT **. Altri esempi di allegati sono i Like su Facebook, i metadati dell'origine del contenuto e le risposte a un messaggio o a un post.  <br/> | `image.gif` <br/> |
    |**MESSAGECLASS** <br/> |Sì  <br/> | Si tratta di una proprietà multivalore, che viene creata e compilata dal connettore partner. Il formato di questa proprietà è  `IPM.NOTE.Source.Event` . Questa proprietà deve iniziare con  `IPM.NOTE` . Questo formato è simile a quello per la  `IPM.NOTE.X` classe messaggio. Questa proprietà include le informazioni seguenti:  <br/><br/>`Source`: indica l'origine dati di terze parti. ad esempio Twitter, Facebook o BlackBerry.  <br/> <br/>  `Event`: indica il tipo di attività eseguita nell'origine dati di terze parti che ha prodotto gli elementi. ad esempio un tweet su Twitter o un post su Facebook. Gli eventi sono specifici per l'origine dati.  <br/> <br/>  Uno scopo di questa proprietà risiede nel filtrare gli elementi specifici in base all'origine dati in cui un elemento ha avuto origine o in base al tipo di evento. In una ricerca eDiscovery, ad esempio, è possibile creare una query di ricerca per trovare tutti i tweet pubblicati da un utente specifico.  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- Quando gli elementi vengono importati correttamente nelle cassette postali in Microsoft 365, un identificatore univoco viene restituito al chiamante come parte della risposta HTTP. Questo identificatore, denominato , può essere utilizzato dai partner per la risoluzione dei problemi successivi per la verifica  `x-IngestionCorrelationID` end-to-end degli elementi. Si consiglia di raccogliere queste informazioni e registrarle nel modo più appropriato. Di seguito è riportato un esempio di una risposta HTTP che mostra l'identificatore:

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- È possibile utilizzare lo strumento Ricerca contenuto nel Centro sicurezza e conformità per cercare gli elementi importati nelle cassette postali da un'origine dati di terze parti. Per cercare in modo specifico questi elementi importati, è possibile utilizzare le seguenti coppie proprietà-valore del messaggio nella casella delle parole chiave per una ricerca di contenuto.
    
  - **`kind:externaldata`**: utilizzare questa coppia proprietà-valore per cercare tutti i tipi di dati di terze parti. Ad esempio, per cercare gli elementi importati da un'origine dati di terze parti e che contenevano la parola "contoso" nella proprietà Subject dell'elemento importato, è necessario utilizzare la query con parole  `kind:externaldata AND subject:contoso` chiave.
    
  - **`itemclass:ipm.externaldata.<third-party data type>`**: utilizzare questa coppia proprietà-valore per cercare solo un tipo specifico di dati di terze parti. Ad esempio, per cercare solo i dati di Facebook che contengono la parola "contoso" nella proprietà Subject, è necessario utilizzare la query con parola  `itemclass:ipm.externaldata.Facebook* AND subject:contoso` chiave. 

  Per un elenco completo dei valori da usare per i tipi di dati di terze parti per la proprietà, vedere Usare Ricerca contenuto per cercare dati di terze parti importati `itemclass` [in Microsoft 365.](use-content-search-to-search-third-party-data-that-was-imported.md)
    
   Per ulteriori informazioni sull'utilizzo di Ricerca contenuto e sulla creazione di query di ricerca con parole chiave, vedere:
    
  - [Ricerca contenuto](content-search.md)
    
  - [Query con parole chiave e condizioni di ricerca per la Ricerca contenuto](keyword-queries-and-search-conditions.md)
