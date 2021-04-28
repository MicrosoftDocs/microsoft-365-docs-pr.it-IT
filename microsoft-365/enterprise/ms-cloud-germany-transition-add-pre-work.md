---
title: Attività di pre-migrazione per la migrazione da Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/09/2021
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
description: 'Riepilogo: pre-lavorare quando si esegue il passaggio da Microsoft Cloud Germania (Microsoft Cloud Deutschland) ai servizi di Office 365 nella nuova area data center tedesca.'
ms.openlocfilehash: 9c3aff56f5d85cd1b98747ef5b747720af74fe02
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073938"
---
# <a name="pre-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Attività di pre-migrazione per la migrazione da Microsoft Cloud Deutschland

Utilizzare questi collegamenti per accedere ai passaggi di pre-migrazione rilevanti per l'organizzazione.

Se si utilizza

- **Office 365 in Microsoft Cloud Deutschland,** eseguire [questa procedura.](#general-tenant-migration-considerations)
- **Domini personalizzati**, eseguire [questo passaggio.](#dns-entries-for-custom-domains)
- **Office Apps**, prendere [in considerazione questo passaggio](#office-apps).
- **SharePoint Online**, eseguire [questo passaggio.](#sharepoint-online)
- **Exchange Online** o **Exchange Hybrid**, eseguire [questo passaggio.](#exchange-online)
- **Skype for Business online,** eseguire [questo passaggio.](#skype-for-business-online)
- **Dynamics 365,** eseguire [questo passaggio.](#dynamics365)
- **Power BI**, eseguire [questo passaggio.](#power-bi)

- **Active Directory Federation Services** per Azure AD Connect, eseguire [questa procedura.](#active-directory-federation-services-ad-fs)
- **Servizi di terze parti** o **app line-of-business (LOB)** integrate con Office 365, eseguire [questo passaggio.](#line-of-business-apps)
- Una soluzione di gestione di dispositivi mobili (MDM) di terze parti, eseguire [questo passaggio.](#mobile-device-management)
- **Servizi di Azure** con l'abbonamento a Office 365, [eseguire questo passaggio.](#microsoft-azure)

## <a name="general-tenant-migration-considerations"></a>Considerazioni generali sulla migrazione dei tenant

**Si applica a:** Tutti i clienti che usano Office 365 nell'istanza di Microsoft Deutschland Cloud

Gli identificatori utente e tenant di Office 365 vengono mantenuti durante la migrazione. Le chiamate al servizio Azure AD vengono reindirizzate da Microsoft Cloud Deutschland ai servizi globali di Office 365 e sono trasparenti per i servizi di Office 365.

- Le richieste DSR (General Data Protection Regulation) (GDPR) vengono eseguite dal portale di amministrazione di Azure per le richieste future. Tutti i dati di diagnostica legacy o non dei clienti residenti in Microsoft Cloud Deutschland vengono eliminati entro 30 giorni.
- Le richieste di autenticazione a più fattori (MFA) che utilizzano Microsoft Authenticator vengono visualizzate come ID oggetto utente (un GUID) mentre il tenant viene copiato nei servizi di Office 365. Le richieste MFA verranno eseguite come previsto nonostante questo comportamento di visualizzazione.  Gli account Microsoft Authenticator attivati tramite endpoint dei servizi di Office 365 visualizzano il nome dell'entità utente (UPN).  Gli account aggiunti tramite gli endpoint di Microsoft Cloud Deutschland visualizzano l'OBJECTID dell'utente, ma funzionano con entrambi gli endpoint dei servizi Microsoft Cloud Deutschland e Office 365.

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Prepararsi a informare gli utenti del riavvio e dell'accesso ai client dopo la migrazione. | Le licenze client di Office passano da Microsoft Cloud Deutschland ai servizi di Office 365 nella migrazione. I client prelevano una nuova licenza valida dopo la disconnessione e l'accesso ai client di Office. | I prodotti Office degli utenti devono aggiornare le licenze dai servizi di Office 365. Se le licenze non vengono aggiornate, i prodotti Office potrebbero verificarsi errori di convalida delle licenze. |
| Verificare la connettività di rete agli URL e agli indirizzi IP dei servizi [di Office 365.](https://aka.ms/o365urls) | Tutti i client e i servizi ospitati dal cliente che vengono utilizzati per accedere al servizio Office 365 devono essere in grado di accedere agli endpoint dei servizi globali di Office 365. <br>Se l'utente o i partner di collaborazione dispongono di regole firewall che impediscono l'accesso agli URL e agli indirizzi IP elencati negli URL e negli indirizzi IP dei servizi di [Office 365,](https://aka.ms/o365urls) è necessario modificare le regole del firewall per consentire l'accesso agli endpoint del servizio globale di Office 365| Se questa operazione non viene eseguita prima della fase 4, possono verificarsi errori del servizio o del software client  |
| Annullare eventuali sottoscrizioni di valutazione. | Le sottoscrizioni di valutazione non verranno migrate e blocteranno il trasferimento delle sottoscrizioni a pagamento. | I servizi di valutazione sono scaduti e non funzionanti se sono accessibili dagli utenti dopo l'annullamento. |
| Analizzare le differenze nelle funzionalità delle licenze tra Microsoft Cloud Deutschland e i servizi globali di Office 365. | I servizi di Office 365 includono funzionalità e servizi aggiuntivi non disponibili nell'attuale Microsoft Cloud Deutschland. Durante il trasferimento dell'abbonamento, le nuove funzionalità saranno disponibili per gli utenti. | <ul><li> Analizzare le diverse funzionalità fornite dalle licenze per Microsoft Cloud Deutschland e i servizi globali di Office 365. Iniziare con la descrizione del servizio della piattaforma [Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) </li><li> Determinare se le nuove funzionalità dei servizi di Office 365 devono essere inizialmente disabilitate per limitare gli effetti sugli utenti o sulla gestione delle modifiche degli utenti e modificare le assegnazioni delle licenze utente in base alle esigenze. </li><li>Preparare gli utenti e il personale dell'help desk per i nuovi servizi e funzionalità forniti dai servizi di Office 365. |
| Creare criteri di [conservazione a livello di organizzazione](https://docs.microsoft.com/microsoft-365/compliance/retention) per proteggere dall'eliminazione accidentale del contenuto durante la migrazione.  |<ul><li>Per assicurarsi che il contenuto non venga inavvertitamente eliminato dagli utenti finali durante la migrazione, i clienti possono scegliere di abilitare un criterio di conservazione a livello di organizzazione. </li><li>Anche se la conservazione non è necessaria, poiché i blocchi inseriti in qualsiasi momento durante la migrazione dovrebbero funzionare come previsto, disporre di un criterio di conservazione è un meccanismo di sicurezza di backup. Allo stesso tempo, un criterio di conservazione potrebbe non essere utilizzato da tutti i clienti, in particolare quelli che sono preoccupati per la conservazione.</li></ul>| Applicare i criteri di conservazione come descritto in [Informazioni sui criteri di conservazione e sulle etichette di conservazione.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) Se questa operazione non viene eseguita prima della fase 4 di 9, possono verificarsi errori del servizio o del software client. </li></ul>|
|||||

## <a name="dns-entries-for-custom-domains"></a>Voci DNS per domini personalizzati

<!-- before phase 9 -->

**Si applica** a : Clienti che impostano un CNAME _msoid_ personalizzato nel proprio dominio DNS o che utilizzano un dominio per Exchange Online

Se configurato, _il CNAME msoid_ interessa solo i clienti che usano il client desktop di Office (Microsoft 365 Apps, Office 365 ProPlus, Office 2019, 2016, ...).

Nel caso in cui sia stato impostato un CNAME DNS denominato _msoid_ in uno o più spazi dei nomi DNS di cui si è proprietari, è necessario rimuovere il CNAME fino alla fine della fase 8 al più tardi. È possibile rimuovere il _msoid_ CNAME in qualsiasi momento prima della fine della fase 8.

Per verificare se è stato impostato un CNAME nello spazio dei nomi DNS, eseguire la _procedura_ seguente e sostituire contoso.com con il proprio nome di dominio:

```console
nslookup -querytype=CNAME msoid.contoso.com
```

Se la riga di comando restituisce un record DNS, rimuovere _il CNAME msoid_ dal dominio.

> [!NOTE]
> Se si utilizza un dominio personalizzato per Exchange Online, è necessario avere accesso al provider di hosting DNS. Assicurarsi di poter accedere alle impostazioni DNS e modificarle durante la migrazione.

## <a name="office-apps"></a>Office Apps

**Si applica a**: I clienti che usano Le app di Office, in particolare nei client Windows <br>
**Se applicato:** ogni volta che inizia la fase 9

I tenant di Office 365 che effettuano la transizione all'area "Germania" richiedono a tutti gli utenti di chiudere, disconnettersi da Office 365 e accedere di nuovo per tutte le applicazioni desktop di Office (Word, Excel, PowerPoint, Outlook e così via) e il client OneDrive for Business dopo che la migrazione del tenant ha raggiunto la fase 9. La disconnessione e l'accesso consentono ai servizi di Office di ottenere nuovi token di autenticazione dal servizio Azure AD globale.

Questa operazione è necessaria per tutti i client. Per garantire un'esperienza di migrazione senza problemi, è consigliabile informare e fornire istruzioni a tutti gli utenti interessati in anticipo e in una fase iniziale di questa prossima attività.

I clienti con client Windows gestiti possono preparare i computer Windows con [lo strumento Office Client Cutover Tool (OCCT).](https://github.com/microsoft/OCCT) La configurazione guidata è progettata per l'esecuzione periodica nei client Windows finché il tenant non raggiunge la fase 9 della migrazione. Una volta raggiunta la fase 9, la OCCT eseguirà automaticamente tutte le modifiche necessarie nel computer senza l'interazione dell'utente.

OCCT può essere distribuito nei client Windows in qualsiasi momento prima della fase 9. Se la configurazione guidata supporta l'esperienza di migrazione, è consigliabile avviare la distribuzione il prima possibile per dotare un numero massimo di client.

## <a name="active-directory-federation-services-ad-fs"></a>Active Directory Federation Services (ADFS)

<!-- before phase 4 -->

**Si applica a**: I clienti che usano AD FS in locale per autenticare gli utenti che si connettono a Microsoft Office 365<br>
**Se applicato:** ogni volta che inizia la fase 4

Leggere e applicare i [passaggi di migrazione adfs](ms-cloud-germany-transition-add-adfs.md)

## <a name="sharepoint-online"></a>SharePoint Online

<!-- before phase 4 -->

**Si applica a**: Clienti che utilizzano SharePoint 2013 locale<br>
**Se applicato:** ogni volta che inizia la fase 4

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Limitare i flussi di lavoro di SharePoint 2013, da utilizzare durante la migrazione di SharePoint Online. | Ridurre i flussi di lavoro di SharePoint 2013 e completare i flussi di lavoro in-flight prima delle transizioni. | L'inazione può causare confusione dell'utente e chiamate all'help desk. |
||||

## <a name="exchange-online"></a>Exchange Online

<!-- before phase 5 -->

**Si applica a**: Clienti di Exchange Online<br>
**Se applicato:** qualsiasi momento prima della fine della fase 9

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Informare i partner esterni della transizione imminente ai servizi di Office 365. |  I clienti devono informare i partner con cui hanno abilitato la condivisione della configurazione del calendario e dello spazio degli indirizzi di disponibilità (consentire la condivisione delle informazioni sulla disponibilità con Office 365). La configurazione della disponibilità deve eseguire la transizione per usare gli endpoint di [Office 365 in](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide) tutto il mondo al termine della migrazione a Exchange Online. | In caso negativo, potrebbe verificarsi un errore del servizio o del client in una fase successiva della migrazione dei clienti. |
| Notificare agli utenti le modifiche necessarie al client IMAP4/POP3/SMTP. | Gli utenti che dispongono di connessioni dei dispositivi agli endpoint Microsoft Cloud Deutschland per i protocolli client IMAP4, POP3, SMTP devono aggiornare manualmente i dispositivi client per passare ai nomi [dei server Exchange Online.](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/pop3-and-imap4#settings-users-use-to-set-up-pop3-or-imap4-access-to-their-exchange-online-mailboxes) | Comunicare in modo preliminare questa dipendenza agli utenti di questi protocolli e assicurarsi che questi possano passare all'utilizzo di Outlook mobile o Outlook sul Web durante questa migrazione. Se non si aggiornano gli endpoint client, si verificano errori di connessione client su Microsoft Cloud Deutschland durante la migrazione delle cassette postali degli utenti. |
||||

### <a name="exchange-online-hybrid-customers"></a>Clienti ibridi di Exchange Online

**Si applica a:** Tutti i clienti che utilizzano una configurazione ibrida di Exchange attiva con server Exchange locali<br>
**Se applicata:** ogni volta che inizia la fase 5

I clienti aziendali con una distribuzione ibrida di Exchange Online e un Exchange Server locale eseguono la procedura guidata di configurazione ibrida (HCW) e AAD Connect per gestire e stabilire la configurazione ibrida. Gli amministratori di Exchange Online Hybrid devono eseguire la procedura guidata di configurazione ibrida  **(HCW)** più volte come parte di questa transizione. Durante la transizione da Microsoft Cloud Deutschland all'area di Office 365 Germany, l'amministratore deve eseguire di nuovo la build più recente di HCW in modalità "Office 365 Germany" prima dell'inizio della migrazione di Exchange (fase 5). Quindi, eseguire di nuovo HCW in modalità "Office 365 Worldwide" al termine della fase 5 per finalizzare la distribuzione locale con le impostazioni dell'area geografica di Office 365 Germany. L'esecuzione di HCW non deve essere eseguita durante la fase 5, ma è importante eseguire HCW solo al termine della fase 5.
Gli attributi della directory vengono sincronizzati tra Office 365 e Azure AD con la distribuzione locale tramite AAD Connect. 

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Eseguire di nuovo HCW con le impostazioni di Office 365 Germany <br><br> <i>È possibile avviare questa attività subito dopo aver ricevuto la notifica del Centro messaggi che indica che la migrazione del tenant di Office 365 è iniziata (fase 1).</i>| La disinstallazione e la riesercizione di HCW (17.0.5378.0 o versione successiva) prima della fase 5 garantiranno che la configurazione locale sia pronta per inviare e ricevere posta sia con gli utenti di Microsoft Cloud Deutschland che con gli utenti migrati nell'area [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) di Office 365 Germany. <p><li> In HCW, per la casella di riepilogo sotto L'organizzazione di **Office 365** è ospitata da , selezionare Office **365 Germany.** | Se non si riesce a completare questa attività prima dell'inizio della fase 5 [migrazione di Exchange], potrebbero verificarsi rapporti di mancato recapito per la posta instradata tra la distribuzione di Exchange locale e Office 365.  
| Conservazione delle impostazioni delle cassette postali condivise | Alcuni clienti ibridi hanno convertito le cassette postali degli utenti cloud in cassette postali "condivise" utilizzando i comandi di Exchange Online. Questa configurazione della cassetta postale cloud viene scritta nella cassetta postale e nella directory locale di Exchange Online, tuttavia, non viene sincronizzata con Active Directory del cliente tramite AAD Connect. Il risultato è una discrepanza tra la rappresentazione di Active Directory dei valori RemoteRecipientType e RemoteDisplayType della cassetta postale e quella in Exchange Online che definisce la cassetta postale come condivisa. <br><br> Il cliente è responsabile di verificare che il provisioning di tutte le cassette postali condivise venga eseguito correttamente utilizzando `New-RemoteMailbox -Shared` `Enable-RemoteMailbox -Shared` , o `Set-RemoteMailbox -Shared` .  Vedere questa guida di riferimento per come convertire la cassetta postale di un utente [in un ambiente ibrido.](/microsoft-365/admin/email/convert-user-mailbox-to-shared-mailbox?view=o365-worldwide)| Se non si riesce a completare questa attività prima della fase 5 [migrazione di Exchange Online], potrebbero verificarsi dei nomi di mancato recapito per le cassette postali condivise che vengono convertite in cassette postali senza licenza e la perdita dell'accesso condiviso per le cassette postali interessate. [Le cassette postali condivise](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes) vengono convertite in modo imprevisto in cassette postali degli utenti dopo l'esecuzione della sincronizzazione della directory in una distribuzione ibrida di Exchange che descrive l'impatto di non risolvere questo problema prima del completamento della migrazione di Exchange Online.  
||||

## <a name="skype-for-business-online"></a>Skype for Business Online

<!-- before phase 7 -->

**Si applica a**: Clienti skype for business online<br>
**Se applicata:** qualsiasi momento prima dell'inizio della fase 7

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Distribuire il client desktop di Teams per gli utenti che accedono a Skype for Business in Germania. | La migrazione sposta gli utenti di Skype for Business in Microsoft Teams per la collaborazione, le chiamate e le chat. Distribuire il client desktop di Microsoft Teams o verificare che sia disponibile un browser supportato. | L'inazione comporta l'inabilità dei servizi di collaborazione di Microsoft Teams. |
| Esaminare e preparare le modifiche DNS correlate alla migrazione. | Modifiche di zona DNS di proprietà del cliente per Skype for Business online. |<ul><li>È consigliabile aggiornare il time-to-live (TTL) per tutti i record DNS di dominio di proprietà del cliente a 5 minuti per accelerare l'aggiornamento dei record DNS. Tuttavia, il cutover gestito da Microsoft associato a questa modifica DNS può verificarsi in qualsiasi momento entro la finestra di modifica di 24 ore fornita. </li><li>L'interruzione del servizio è possibile in futuro. Gli utenti non potranno accedere a Skype for Business e verranno reindirizzati all'esperienza di Teams migrata nei servizi di Office 365. </li></ul>|
| Preparare la formazione e la preparazione per l'utente finale e l'amministrazione per la transizione a Microsoft Teams. | Avere successo nella transizione da Skype a Teams pianificando la comunicazione e la preparazione degli utenti. | <ul><li>I client devono essere a conoscenza dei nuovi servizi e delle modalità di utilizzo dopo la transizione dei servizi ai servizi di Office 365. </li><li>Dopo aver apportato modifiche al DNS sia per i domini di vanità dei clienti che per il dominio iniziale, gli utenti accederebbero a Skype for Business e vedevano che ora vengono migrati in Teams. In questo modo si scarica anche il client desktop per Teams in background. </li></ul>|
||||

## <a name="mobile-device-management"></a>Gestione dei dispositivi mobili

<!-- before phase 5 -->
**Si applica a:** Clienti che usano una soluzione di gestione di dispositivi mobili (MDM) di terze parti<br>
**Se applicato:** ogni volta che inizia la fase 5

| Step(s) | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Preparare la formazione per l'utente finale e l'amministrazione sugli utenti che rimuovono e aggiungono di nuovo il proprio account a Microsoft Outlook per iOS e Android. | Gli account di Microsoft Outlook per iOS e Android configurati con cassette postali in Microsoft Cloud Deutschland potrebbero essere rimossi e aggiunti di nuovo a Outlook per sincronizzare correttamente la nuova configurazione dei servizi di Office 365. | Clienti di Microsoft Outlook per iOS e Android | Le cassette postali di Outlook configurate in precedenza per Microsoft Cloud Deutschland potrebbero non riprendere la nuova configurazione dei servizi di Office 365, causando errori e peggiorando le prestazioni di altre esperienze utente. Gli amministratori IT sono invitati a fornire documentazione che istruisce in modo proattivo gli utenti a rimuovere e aggiungere di nuovo i propri account a Microsoft Outlook per iOS e Android se si verificano problemi con l'accesso o la sincronizzazione della posta dopo la migrazione. |
| Determinare se è necessaria una riconfigurazione dopo la migrazione. | Le soluzioni di gestione dei dispositivi mobili (MDM, Mobile Device Management) possono essere di destinazione `outlook.de` degli endpoint. In questa transizione ai servizi di Office 365, i profili client devono essere aggiornati all'URL dei servizi di Office 365, `outlook.office365.com` . | Clienti di Exchange Online e MDM | I client potrebbero continuare a funzionare mentre l'endpoint è accessibile, ma non riusciranno se `outlook.de` gli endpoint di Microsoft Cloud Deutschland non sono più disponibili. |
|||||

## <a name="line-of-business-apps"></a>App line-of-business

**Si applica a:** Clienti che usano app line-of-business (LOB) con endpoint forniti da Microsoft Cloud Deutschland<br>
**Se applicato:** dopo il completamento della fase 2 e prima della fine della fase 9

Se si usa un servizio di terze parti o app line-of-business (LOB) integrate con Office 365, è necessario risolvere eventuali dipendenze dagli endpoint forniti dall'istanza di Microsoft Cloud Deutschland. Ad esempio, se le app LOB si connettono a `https://graph.microsoft.de/` , devi modificare l'endpoint in `https://graph.microsoft.com/` . Gli endpoint del servizio globale Microsoft Office 365 diventano disponibili per il tenant dopo la fase 2.

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Determinare se è necessaria una riconfigurazione dopo la migrazione. | I servizi e le applicazioni di terze parti che si integrano con Office 365 possono essere codificati per prevedere indirizzi IP e URL di Microsoft Cloud Deutschland. | Azione obbligatoria. L'inazione può causare errori del servizio o del software client. |
||||

## <a name="dynamics-365"></a>Dynamics 365

**Si applica a:** Clienti che utilizzano Microsoft Dynamics 365

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Per le sottoscrizioni sandbox di Dynamics 365, assicurati di scaricare l'ambiente di produzione dell'istanza di Dynamics SQL dall'abbonamento Dynamics 365 in Microsoft Cloud Deutschland. Il backup di produzione più recente deve essere ripristinato nella sandbox prima della migrazione sandbox. | La migrazione di Dynamics 365 richiede ai clienti di verificare che l'ambiente sandbox sia aggiornato con il database di produzione più recente. | Il team di FastTrack assisterà i clienti nell'esecuzione di esecuzioni a secco per convalidare l'aggiornamento della versione da 8.x a 9.1.x. |
||||

## <a name="power-bi"></a>Power BI

**Si applica a:** Clienti che usano Power BI

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Rimozione di oggetti dalle sottoscrizioni di Power BI che non verranno migrate da Power BI Microsoft Cloud Deutschland ai servizi di Office 365. | La migrazione dei servizi Power BI richiederà l'intervento del cliente per eliminare determinati elementi, ad esempio set di dati e dashboard. | <ul><li>Gli amministratori potrebbero essere necessario rimuovere gli elementi seguenti dalla sottoscrizione: </li><li>Real-Time set di dati (ad esempio, set di dati di streaming o push) </li><li>Origine dati e configurazione del gateway dati locale di Power BI </li></ul>|
||||

## <a name="microsoft-azure"></a>Microsoft Azure

Se si usa la stessa partizione di identità di Azure Active Directory per Office 365 e Microsoft Azure nell'istanza di Microsoft Cloud Deutschland, assicurarsi di prepararsi per la migrazione dei servizi di Microsoft Azure guidata dal cliente.

> [!NOTE]
> La migrazione dei servizi di Microsoft Azure non deve essere avviata prima che il tenant di Office 365 raggiunga la fase di migrazione 3 e deve essere completata prima del completamento della fase di migrazione 8.

I clienti che usano le risorse di Office 365 e Azure (ad esempio, rete, calcolo e archiviazione) eseguiranno la migrazione delle risorse all'istanza dei servizi di Office 365. Questa migrazione è responsabilità del cliente. I post del Centro messaggi segnaleranno l'inizio. La migrazione deve essere completata prima della finalizzazione dell'organizzazione di Azure AD nell'ambiente dei servizi di Office 365. Per le migrazioni di Azure, vedere il playbook sulla migrazione di Azure, [Panoramica delle indicazioni per la migrazione per Azure Germania.](https://docs.microsoft.com/azure/germany/germany-migration-main)

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Determinare quali servizi di Azure sono in uso e prepararsi per la migrazione futura dalla Germania al tenant dei servizi di Office 365 collaborando con i partner. Seguire i passaggi descritti nel [playbook di migrazione di Azure](/azure/germany/germany-migration-main). |<ul><li>La migrazione delle risorse di Azure è una responsabilità del cliente e richiede sforzi manuali seguendo i passaggi prescritti. La comprensione dei servizi in uso nell'organizzazione è fondamentale per la corretta migrazione dei servizi di Azure. </li><li> I clienti di Office 365 Germany che dispongono di sottoscrizioni di Azure nella stessa partizione di identità (organizzazione) devono seguire l'ordine prescritto da Microsoft quando possono iniziare la migrazione di sottoscrizione e servizi.</li></ul>|<ul><li>I clienti possono avere più sottoscrizioni di Azure, ogni sottoscrizione contenente infrastruttura, servizi e componenti della piattaforma. </li><li> Gli amministratori devono identificare le sottoscrizioni e le parti interessate per garantire che la migrazione e la convalida tempestive siano possibili nell'ambito di questo evento di migrazione. </li><li>Se non si riesce a completare correttamente la migrazione di queste sottoscrizioni e componenti di Azure entro la sequenza temporale prescritta, il completamento della transizione di Office e Azure AD ai servizi di Office 365 può causare la perdita di dati. </li><li> Una notifica del Centro messaggi segnalerà il punto in cui può iniziare la migrazione guidata dal cliente. </li></ul>|
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

- [Migrazione da Microsoft Cloud Deutschland ai servizi di Office 365 nelle nuove aree data center tedesche](ms-cloud-germany-transition.md)
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
