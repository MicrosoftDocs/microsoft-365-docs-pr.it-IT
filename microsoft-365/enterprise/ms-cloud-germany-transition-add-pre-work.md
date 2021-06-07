---
title: Attività di pre-migrazione per la migrazione da Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 05/12/2021
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Riepilogo: pre-lavorare quando si esegue il passaggio da Microsoft Cloud Germania (Microsoft Cloud Deutschland) a Office 365 servizi nella nuova area data center tedesca.'
ms.openlocfilehash: 5eefa56b96eb616c694b26c374b235ccd95c3ee9
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796019"
---
# <a name="pre-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Attività di pre-migrazione per la migrazione da Microsoft Cloud Deutschland

Utilizzare questi collegamenti per accedere ai passaggi di pre-migrazione rilevanti per l'organizzazione.

Se si utilizza

- **Office 365 in Microsoft Cloud Deutschland,** procedere [come segue.](#general-tenant-migration-considerations)
- **Domini personalizzati**, eseguire [questo passaggio.](#dns-entries-for-custom-domains)
- **Office app**, prendere [in considerazione questo passaggio.](#office-apps)
- **SharePoint Online**, eseguire [questo passaggio.](#sharepoint-online)
- **Exchange Online** o **Exchange ibrido**, eseguire [questo passaggio.](#exchange-online)
- **Skype for Business Online**, eseguire [questo passaggio.](#skype-for-business-online)
- **Dynamics 365,** eseguire [questo passaggio.](#dynamics365)
- **Power BI**, eseguire [questo passaggio.](#power-bi)
- **Active Directory Federation Services** per Azure AD Connessione, eseguire [questa procedura.](#active-directory-federation-services-ad-fs)
- **Eseguire questo passaggio** per i servizi di terze parti o le app **line-of-business (LOB)** integrate con Office 365, [eseguire questo passaggio.](#line-of-business-apps)
- Una soluzione di gestione di dispositivi mobili (MDM) di terze parti, eseguire [questo passaggio.](#mobile-device-management)
- **Azure services** with your Office 365 subscription, do [this step](#microsoft-azure).

## <a name="general-tenant-migration-considerations"></a>Considerazioni generali sulla migrazione dei tenant

**Si applica a:** Tutti i clienti che Office 365 nell'istanza di Microsoft Deutschland Cloud

Office 365 tenant e gli identificatori utente vengono mantenuti durante la migrazione. Le chiamate al servizio Azure AD vengono reindirizzate da Microsoft Cloud Deutschland ai Office 365 globali e sono trasparenti per Office 365 servizi.

- Le richieste DSR (General Data Protection Regulation) (GDPR) vengono eseguite dal portale di amministrazione di Azure per le richieste future. Tutti i dati di diagnostica legacy o non dei clienti residenti in Microsoft Cloud Deutschland vengono eliminati entro 30 giorni.
- Le richieste MFA (Multi-Factor Authentication) che utilizzano Microsoft Authenticator vengono visualizzate come ID oggetto utente (un GUID) mentre il tenant viene copiato Office 365 servizi. Le richieste MFA verranno eseguite come previsto nonostante questo comportamento di visualizzazione.  Microsoft Authenticator gli account attivati tramite Office 365 endpoint dei servizi di configurazione visualizzano il nome dell'entità utente (UPN).  Gli account aggiunti tramite gli endpoint di Microsoft Cloud Deutschland visualizzano l'OBJECTID dell'utente, ma funzionano con gli endpoint di Microsoft Cloud Deutschland e Office 365 services.

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Prepararsi a informare gli utenti del riavvio e dell'accesso ai client dopo la migrazione. | Office licenze client verranno transizione da Microsoft Cloud Deutschland a Office 365 servizi nella migrazione. I client prelevano una nuova licenza valida dopo la disconnessione e l'accesso a Office client. | I prodotti Office devono aggiornare le licenze dai Office 365 aziendali. Se le licenze non vengono aggiornate, Office potrebbero verificarsi errori di convalida delle licenze. |
| Verificare la connettività di [rete Office 365 URL e indirizzi IP dei servizi.](https://aka.ms/o365urls) | Tutti i client e i servizi ospitati dal cliente che vengono utilizzati per accedere Office 365 servizio devono essere in grado di accedere Office 365 endpoint dei servizi globali. <br>Nel caso in cui l'utente o i partner di collaborazione presentino regole firewall che impediscono l'accesso agli URL e agli indirizzi IP elencati negli URL e negli indirizzi IP dei servizi [Office 365,](https://aka.ms/o365urls) è necessario modificare le regole del firewall per consentire l'accesso agli endpoint del servizio globale di Office 365| Se questa operazione non viene eseguita prima della fase 4, possono verificarsi errori del servizio o del software client  |
| Annullare eventuali sottoscrizioni di valutazione. | Le sottoscrizioni di valutazione non verranno migrate e blocteranno il trasferimento delle sottoscrizioni a pagamento. | I servizi di valutazione sono scaduti e non funzionanti se sono accessibili dagli utenti dopo l'annullamento. |
| Analizzare le differenze nelle funzionalità delle licenze tra Microsoft Cloud Deutschland e i Office 365 Global Services. | Office 365 includono funzionalità e servizi aggiuntivi non disponibili nell'attuale Microsoft Cloud Deutschland. Durante il trasferimento dell'abbonamento, le nuove funzionalità saranno disponibili per gli utenti. | <ul><li> Analizzare le diverse funzionalità fornite dalle licenze per Microsoft Cloud Deutschland e Office 365 Global Services. Iniziare con la [descrizione Office 365 del servizio della piattaforma.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) </li><li> Determinare se le nuove funzionalità dei Office 365 devono essere inizialmente disabilitate per limitare gli effetti sugli utenti o sulla gestione delle modifiche degli utenti e modificare le assegnazioni delle licenze utente in base alle esigenze. </li><li>Preparare gli utenti e il personale dell'help desk per i nuovi servizi e funzionalità forniti Office 365 servizi. |
| Creare criteri di [conservazione a livello di organizzazione](https://docs.microsoft.com/microsoft-365/compliance/retention) per proteggere dall'eliminazione accidentale del contenuto durante la migrazione.  |<ul><li>Per assicurarsi che il contenuto non venga inavvertitamente eliminato dagli utenti finali durante la migrazione, i clienti possono scegliere di abilitare un criterio di conservazione a livello di organizzazione. </li><li>Anche se la conservazione non è necessaria, poiché i blocchi inseriti in qualsiasi momento durante la migrazione dovrebbero funzionare come previsto, disporre di un criterio di conservazione è un meccanismo di sicurezza di backup. Allo stesso tempo, un criterio di conservazione potrebbe non essere utilizzato da tutti i clienti, in particolare quelli che sono preoccupati per la conservazione.</li></ul>| Applicare i criteri di conservazione come descritto in [Informazioni sui criteri di conservazione e sulle etichette di conservazione.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) Se questa operazione non viene eseguita prima della fase 4 di 9, possono verificarsi errori del servizio o del software client. </li></ul>|
|||||

## <a name="dns-entries-for-custom-domains"></a>Voci DNS per domini personalizzati

<!-- before phase 9 -->

**Si applica** a : Clienti che impostano un CNAME _msoid_ personalizzato nel proprio dominio DNS o utilizzano un dominio per Exchange Online

Se configurato, il CNAME _msoid_ influisce solo sui clienti che usano un client desktop Office (Microsoft 365 Apps, Office 365 ProPlus, Office 2019, 2016, ...).

Nel caso in cui sia stato impostato un CNAME DNS denominato _msoid_ in uno o più spazi dei nomi DNS di cui si è proprietari, è necessario rimuovere il CNAME fino alla fine della fase 8 al più tardi. È possibile rimuovere il _msoid_ CNAME in qualsiasi momento prima della fine della fase 8.

Per verificare se è stato impostato un CNAME nello spazio dei nomi DNS, eseguire la _procedura_ seguente e sostituire contoso.com con il proprio nome di dominio:

```console
nslookup -querytype=CNAME msoid.contoso.com
```

Se la riga di comando restituisce un record DNS, rimuovere _il CNAME msoid_ dal dominio.

> [!NOTE]
> Se si utilizza un dominio personalizzato per Exchange Online, è necessario avere accesso al provider di hosting DNS. Assicurarsi di poter accedere alle impostazioni DNS e modificarle durante la migrazione.

## <a name="office-apps"></a>Office App

**Si applica a:** Clienti che usano app Office, in particolare nei Windows client <br>
**Se applicato:** ogni volta che inizia la fase 9

i tenant di Office 365 in transizione all'area "Germania" richiedono a tutti gli utenti di chiudere, disconnettersi da Office 365 e accedere di nuovo per tutte le applicazioni desktop Office (Word, Excel, PowerPoint, Outlook e così via) e il client OneDrive for Business dopo che la migrazione tenant ha raggiunto la fase 9. La disconnessione e l'accesso consentono ai Office di ottenere nuovi token di autenticazione dal servizio globale di Azure AD.

Questa operazione è necessaria per tutti i client. Per garantire un'esperienza di migrazione senza problemi, è consigliabile informare e fornire istruzioni a tutti gli utenti interessati in anticipo e in una fase iniziale di questa prossima attività.

I clienti con Windows client gestiti possono preparare Windows computer con lo Office [Client Cutover Tool (OCCT)](https://github.com/microsoft/OCCT). La configurazione guidata è progettata per l'esecuzione periodica Windows client finché il tenant non raggiunge la fase 9 della migrazione. Una volta raggiunta la fase 9, la OCCT eseguirà automaticamente tutte le modifiche necessarie nel computer senza l'interazione dell'utente.

La OCCT può essere distribuita Windows client in qualsiasi momento prima della fase 9. Se la configurazione guidata supporta l'esperienza di migrazione, è consigliabile avviare la distribuzione il prima possibile per dotare un numero massimo di client.

## <a name="active-directory-federation-services-ad-fs"></a>Active Directory Federation Services (ADFS)

**Si applica a**: I clienti che usano AD FS in locale per autenticare gli utenti che si connettono a Microsoft Office 365<br>
**Se applicata:** qualsiasi momento prima dell'inizio della fase 2

Leggere e applicare i [passaggi di migrazione adfs](ms-cloud-germany-transition-add-adfs.md)

## <a name="sharepoint-online"></a>SharePoint Online

**Si applica a:** Clienti che SharePoint 2013 locale<br>
**Se applicato:** ogni volta che inizia la fase 4

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Limitare SharePoint flussi di lavoro 2013, da utilizzare durante la SharePoint online. | Ridurre SharePoint flussi di lavoro 2013 e completare i flussi di lavoro in-flight prima delle transizioni. | L'inazione può causare confusione dell'utente e chiamate all'help desk. |
||||

## <a name="exchange-online"></a>Exchange Online

<!-- before phase 5 -->

**Si applica a**: Exchange Online clienti<br>
**Se applicato:** qualsiasi momento prima della fine della fase 9

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Informare i partner esterni della transizione imminente Office 365 servizi. |  I clienti devono informare i partner con cui hanno abilitato la condivisione della configurazione del calendario e dello spazio degli indirizzi di disponibilità (consentire la condivisione delle informazioni sulla disponibilità con Office 365). La configurazione della disponibilità deve eseguire la transizione per [usare Office 365 endpoint](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide) globali al termine Exchange Online migrazione. | In caso negativo, potrebbe verificarsi un errore del servizio o del client in una fase successiva della migrazione dei clienti. |
| Notificare agli utenti le modifiche necessarie al client IMAP4/POP3/SMTP. | Gli utenti che dispongono di connessioni dispositivo agli endpoint Microsoft Cloud Deutschland per i protocolli client IMAP4, POP3, SMTP devono aggiornare manualmente i dispositivi client per passare ai nomi dei [server Exchange Online](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/pop3-and-imap4#settings-users-use-to-set-up-pop3-or-imap4-access-to-their-exchange-online-mailboxes). | Comunicare in modo preliminare questa dipendenza agli utenti di questi protocolli e assicurarsi che questi possano passare all'Outlook mobile o Outlook sul Web durante la migrazione. Se non si aggiornano gli endpoint client, si verificano errori di connessione client su Microsoft Cloud Deutschland durante la migrazione delle cassette postali degli utenti. |
||||

### <a name="exchange-online-hybrid-customers"></a>Exchange Online Clienti ibridi

**Si applica a:** Tutti i clienti che usano una configurazione ibrida Exchange con Exchange server locali<br>
**Se applicata:** ogni volta che inizia la fase 5

Enterprise clienti con una distribuzione ibrida di Exchange Online e un Exchange Server locale eseguire la procedura guidata di configurazione ibrida (HCW) e AAD Connessione per mantenere e stabilire la configurazione ibrida. Exchange Online Gli amministratori ibridi devono eseguire la procedura guidata di configurazione ibrida **(HCW)** più volte come parte di questa transizione. Durante la transizione da Microsoft Cloud Deutschland all'area di Office 365 Germania, l'amministratore deve eseguire di nuovo la build più recente di HCW in modalità "Office 365 Germania" prima dell'inizio della migrazione di Exchange (fase 5). Quindi, esegui di nuovo HCW in modalità "Office 365 Worldwide" al termine della fase 5 per finalizzare la distribuzione locale con le impostazioni dell'area Office 365 Germania. L'esecuzione di HCW non deve essere eseguita durante la fase 5, ma è importante eseguire HCW solo al termine della fase 5.
Gli attributi della directory vengono sincronizzati tra Office 365 e Azure AD con la distribuzione locale tramite AAD Connessione. 

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Eseguire di nuovo HCW usando Office 365 Germania <br><br> <i>È possibile avviare questa attività subito dopo aver ricevuto la notifica del centro messaggi che indica che la migrazione del tenant Office 365 è iniziata (fase 1).</i>| La disinstallazione e la riesercizione di HCW (17.0.5378.0 o versione successiva) prima della fase 5 garantiranno che la configurazione locale sia pronta per inviare e ricevere posta sia con gli utenti di Microsoft Cloud Deutschland che con gli utenti migrati [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) Office 365 Germania. <p><li> In HCW, per la casella di riepilogo sotto **My Office 365 organization is hosted by** selezionare Office 365 **Germany.** | La mancata esecuzione di questa attività prima dell'inizio della fase 5 [migrazione di Exchange] può comportare rapporti di mancato recapito per la posta instradata tra la distribuzione di Exchange locale e Office 365.  
| Conservazione delle impostazioni delle cassette postali condivise | Alcuni clienti ibridi hanno convertito le cassette postali degli utenti cloud in cassette postali "condivise" Exchange Online comandi. Questa configurazione della cassetta postale cloud viene scritta nella cassetta postale e nella directory Exchange Online locale, tuttavia, non viene sincronizzata con Active Directory del cliente tramite AAD Connessione. Il risultato è una discrepanza tra la rappresentazione di Active Directory dei valori RemoteRecipientType e RemoteDisplayType della cassetta postale e quella in Exchange Online la definizione della cassetta postale come condivisa. <br><br> Il cliente è responsabile di verificare che il provisioning di tutte le cassette postali condivise venga eseguito correttamente utilizzando `New-RemoteMailbox -Shared` `Enable-RemoteMailbox -Shared` , o `Set-RemoteMailbox -Shared` .  Vedere questa guida di riferimento per come convertire la cassetta postale di un utente [in un ambiente ibrido.](/microsoft-365/admin/email/convert-user-mailbox-to-shared-mailbox?view=o365-worldwide)| Se non si riesce a completare questa attività prima della fase 5 [migrazione di Exchange Online], potrebbero verificarsi dei nomi di mancato recapito per le cassette postali condivise che vengono convertite in cassette postali senza licenza e la perdita dell'accesso condiviso per le cassette postali interessate. [Le cassette postali](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes) condivise vengono convertite in modo imprevisto in cassette postali degli utenti dopo l'esecuzione della sincronizzazione della directory in una distribuzione ibrida di Exchange descrive l'impatto di non risolvere questo problema prima del completamento della Exchange Online migrazione.  
||||

## <a name="skype-for-business-online"></a>Skype for Business Online

<!-- before phase 7 -->

**Si applica a**: Skype For Business Online<br>
**Se applicata:** qualsiasi momento prima dell'inizio della fase 7

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Distribuire Teams client desktop per gli utenti che accedono Skype for Business in Germania. | La migrazione Skype for Business utenti a Microsoft Teams collaborazione, chiamata e chat. Distribuire il client Microsoft Teams desktop o verificare che sia disponibile un browser supportato. | L'inazione comporta l'invariabilità Microsoft Teams servizi di collaborazione. |
| Esaminare e preparare le modifiche DNS correlate alla migrazione. | Modifiche di zona DNS di proprietà del cliente per Skype for Business Online. |<ul><li>È consigliabile aggiornare il time-to-live (TTL) per tutti i record DNS di dominio di proprietà del cliente a 5 minuti per accelerare l'aggiornamento dei record DNS. Tuttavia, il cutover gestito da Microsoft associato a questa modifica DNS può verificarsi in qualsiasi momento entro la finestra di modifica di 24 ore fornita. </li><li>L'interruzione del servizio è possibile in futuro. Gli utenti non potranno accedere a Skype for Business e verranno reindirizzati all'esperienza di Teams migrata nei servizi Office 365 migrazione. </li></ul>|
| Preparare la formazione e la preparazione dell'utente finale e dell'amministrazione per la transizione a Microsoft Teams. | Avere successo nella transizione da Skype a Teams pianificando la comunicazione e la preparazione degli utenti. | <ul><li>I client devono essere a conoscenza dei nuovi servizi e delle modalità di utilizzo dopo la transizione dei servizi ai Office 365 servizi. </li><li>Dopo aver apportato modifiche DNS sia per i domini di vanità dei clienti che per il dominio iniziale, gli utenti accederanno a Skype for Business e potranno vedere che ora vengono migrati a Teams. In questo modo si scarica anche il client desktop per Teams in background. </li></ul>|
||||

## <a name="mobile-device-management"></a>Gestione dei dispositivi mobili

<!-- before phase 5 -->
**Si applica a:** Clienti che usano una soluzione di gestione di dispositivi mobili (MDM) di terze parti<br>
**Se applicato:** ogni volta che inizia la fase 5

| Step(s) | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Preparare la formazione per gli utenti finali e per l'amministrazione sulla rimozione e la ri-aggiunta del proprio account a Microsoft Outlook per iOS e Android. | Potrebbe essere necessario rimuovere e aggiungere di nuovo a Outlook gli account Microsoft Outlook per iOS e Android configurati con cassette postali in Microsoft Cloud Deutschland per sincronizzare correttamente la nuova configurazione dei servizi Office 365. | Microsoft Outlook per clienti iOS e Android | Outlook cassette postali configurate in precedenza per Microsoft Cloud Deutschland potrebbero non riprendere la nuova configurazione di Office 365 Services, causando errori e prestazioni ridotte di altre esperienze utente. Gli amministratori IT sono invitati a fornire documentazione che istruisce in modo proattivo gli utenti a rimuovere e aggiungere di nuovo i propri account a Microsoft Outlook per iOS e Android se si verificano problemi con l'accesso o la sincronizzazione della posta dopo la migrazione. |
| Determinare se è necessaria una riconfigurazione dopo la migrazione. | Le soluzioni di gestione dei dispositivi mobili (MDM, Mobile Device Management) possono essere di destinazione `outlook.de` degli endpoint. In questa transizione a Office 365 Services, i profili client devono essere aggiornati all'URL Office 365 services, `outlook.office365.com` . | Exchange Online e MDM | I client potrebbero continuare a funzionare mentre l'endpoint è accessibile, ma non riusciranno se `outlook.de` gli endpoint di Microsoft Cloud Deutschland non sono più disponibili. |
|||||

## <a name="line-of-business-apps"></a>App line-of-business

**Si applica a:** Clienti che usano app line-of-business (LOB) con endpoint forniti da Microsoft Cloud Deutschland<br>
**Se applicato:** dopo il completamento della fase 2 e prima della fine della fase 9

Se si usa un servizio di terze parti o app line-of-business integrate con Office 365, è necessario risolvere eventuali dipendenze dagli endpoint forniti dall'istanza di Microsoft Cloud Deutschland. Ad esempio, se le app LOB si connettono a `https://graph.microsoft.de/` , devi modificare l'endpoint in `https://graph.microsoft.com/` . Gli endpoint del servizio Microsoft Office 365 globale diventano disponibili per il tenant dopo la fase 2.

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Determinare se è necessaria una riconfigurazione dopo la migrazione. | I servizi e le applicazioni di terze parti che si integrano con Office 365 possono essere codificati per prevedere indirizzi IP e URL di Microsoft Cloud Deutschland. | Azione obbligatoria. L'inazione può causare errori del servizio o del software client. |
||||

## <a name="dynamics-365"></a>Dynamics 365

**Si applica a:** Clienti che utilizzano Microsoft Dynamics 365

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Per le sottoscrizioni sandbox di Dynamics 365, assicurati di scaricare l'ambiente di produzione dell'istanza di Dynamics SQL dalla sottoscrizione Dynamics 365 in Microsoft Cloud Deutschland. Il backup di produzione più recente deve essere ripristinato nella sandbox prima della migrazione sandbox. | La migrazione di Dynamics 365 richiede ai clienti di verificare che l'ambiente sandbox sia aggiornato con il database di produzione più recente. | Il team di FastTrack assisterà i clienti nell'esecuzione di esecuzioni a secco per convalidare l'aggiornamento della versione da 8.x a 9.1.x. |
||||

## <a name="power-bi"></a>Power BI

**Si applica a**: Clienti che usano Power BI

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Rimozione di oggetti da Power BI sottoscrizioni che non verranno migrate da Power BI Microsoft Cloud Deutschland a Office 365 servizi. | La migrazione dei Power BI richiederà l'intervento del cliente per eliminare determinati elementi, ad esempio set di dati e dashboard. | <ul><li>Gli amministratori potrebbero essere necessario rimuovere gli elementi seguenti dalla sottoscrizione: </li><li>Real-Time set di dati (ad esempio, set di dati di streaming o push) </li><li>Power BI configurazione e origine dati del gateway dati locale </li></ul>|
||||

## <a name="microsoft-azure"></a>Microsoft Azure

Se si utilizza la stessa partizione di identità di Azure Active Directory per Office 365 e Microsoft Azure nell'istanza di Microsoft Cloud Deutschland, assicurarsi di prepararsi per la migrazione guidata dal cliente dei servizi Microsoft Azure.

> [!NOTE]
> La migrazione dei servizi di Microsoft Azure potrebbe non essere avviata prima che il tenant di Office 365 raggiunga la fase di migrazione 9 e deve essere completata prima dell'avvio della fase 10.

I clienti che usano Office 365 e le risorse di Azure (ad esempio, rete, calcolo e archiviazione) eseguiranno la migrazione delle risorse all'istanza Office 365 services. Questa migrazione è responsabilità del cliente. I post del Centro messaggi segnaleranno l'inizio. La migrazione deve essere completata prima della finalizzazione dell'organizzazione di Azure AD nell'ambiente Office 365 services. Per le migrazioni di Azure, vedere il playbook sulla migrazione di Azure, [Panoramica delle indicazioni per la migrazione per Azure Germania.](https://docs.microsoft.com/azure/germany/germany-migration-main)

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Determinare quali servizi di Azure sono in uso e prepararsi per la migrazione futura dalla Germania al tenant Office 365 services collaborando con i partner. Seguire i passaggi descritti nel [playbook di migrazione di Azure](/azure/germany/germany-migration-main). |<ul><li>La migrazione delle risorse di Azure è una responsabilità del cliente e richiede sforzi manuali seguendo i passaggi prescritti. La comprensione dei servizi in uso nell'organizzazione è fondamentale per la corretta migrazione dei servizi di Azure. </li><li> Office 365 I clienti tedeschi che dispongono di sottoscrizioni di Azure nella stessa partizione di identità (organizzazione) devono seguire l'ordine prescritto da Microsoft quando possono iniziare la migrazione di sottoscrizione e servizi.</li></ul>|<ul><li>I clienti possono avere più sottoscrizioni di Azure, ogni sottoscrizione contenente infrastruttura, servizi e componenti della piattaforma. </li><li> Gli amministratori devono identificare le sottoscrizioni e le parti interessate per garantire che la migrazione e la convalida tempestive siano possibili nell'ambito di questo evento di migrazione. </li><li>Se non si riesce a completare correttamente la migrazione di queste sottoscrizioni e componenti di Azure entro la sequenza temporale prescritta, il completamento della transizione di Office e Azure AD ai servizi di Office 365 può causare la perdita di dati. </li><li> Una notifica del Centro messaggi segnalerà il punto in cui può iniziare la migrazione guidata dal cliente. </li></ul>|
||||

<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](/azure/germany/germany-migration-main).

**Description:** Migration of Azure resources is a customer responsibility and requires manual effort following prescribed steps. Understanding what services are in use in the organization is key to successful migration of Azure services. 

Office 365 Germany customers who have Azure subscriptions under the same identity partition (organization) must follow the Microsoft-prescribed order when they can begin subscription and services migration.

**Applies to:** Azure Customers

**Impact:** 

- Customers may have multiple Azure subscriptions, each subscription containing infrastructure, services, and platform components. 
- Administrators should identify subscriptions and stakeholders to ensure prompt migration and validation is possible as part of this migration event.

  Failing to successfully complete migration of these subscriptions and Azure components within the prescribed timeline will affect completion of the Office and Azure AD transition to Office 365 services and may result in data loss.
- A Message center notification will signal the point at which customer-led migration can begin.
-->

## <a name="more-information"></a>Ulteriori informazioni

Guida introduttiva:

- [Migrazione da Microsoft Cloud Deutschland ai servizi Office 365 nelle nuove aree data center tedesche](ms-cloud-germany-transition.md)
- [Assistenza per la migrazione di Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Come acconsentire esplicitamente a eseguire la migrazione](ms-cloud-germany-migration-opt-in.md)
- [Esperienza del cliente durante la migrazione](ms-cloud-germany-transition-experience.md)

Passaggio attraverso la transizione:

- [Azioni ed impatti sulle fasi della migrazione](ms-cloud-germany-transition-phases.md)
- [Pre-lavoro aggiuntivo](ms-cloud-germany-transition-add-pre-work.md)
- Informazioni aggiuntive per [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivi,](ms-cloud-germany-transition-add-devices.md) [esperienze](ms-cloud-germany-transition-add-experience.md)e [ADFS.](ms-cloud-germany-transition-add-adfs.md)

App cloud:

- [Informazioni sul programma di migrazione di Dynamics 365](/dynamics365/get-started/migrate-data-german-region)
- [Informazioni sul programma di migrazione di Power BI](/power-bi/admin/service-admin-migrate-data-germany)
- [Guida introduttiva all'aggiornamento di Microsoft Teams](/microsoftteams/upgrade-start-here)
