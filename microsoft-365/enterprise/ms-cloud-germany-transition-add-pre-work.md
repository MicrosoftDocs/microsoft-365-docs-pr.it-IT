---
title: Pre-lavoro per la migrazione da Microsoft Cloud Deutschland
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
ms.openlocfilehash: 5110c6bd86d5df35a7ceccb4abfedf059cb826d0
ms.sourcegitcommit: 450661071e44854f0a0a92af648f76d907767b71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2021
ms.locfileid: "50826177"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>Pre-lavoro per la migrazione da Microsoft Cloud Deutschland

Utilizzare questi collegamenti per accedere ai passaggi pre-lavorativi rilevanti per l'organizzazione:

- Per tutti i clienti che usano Office 365 in Microsoft Cloud Deutschland, eseguire [questa procedura.](#applies-to-everyone)
- Se si utilizza Exchange Online o exchange ibrido, eseguire [questo passaggio.](#exchange-online)
- Se si utilizza SharePoint Online, eseguire [questo passaggio.](#sharepoint-online)
- Se si usa una soluzione di gestione dei dispositivi mobili (MDM) di terze parti, eseguire [questo passaggio.](#mobile)
- Se si usano app line-of-business o di servizi di terze parti integrate con Office 365, eseguire [questo passaggio.](#line-of-business-apps)
- Se si usano anche servizi di Azure oltre a quelli inclusi nell'abbonamento a Office 365, eseguire [questo passaggio.](#microsoft-azure)
- Se si usa anche Dynamics 365, eseguire [questo passaggio.](#dynamics365)
- Se si usa anche Power BI, eseguire [questo passaggio.](#power-bi)
- Per le modifiche al DNS, [eseguire questo passaggio.](#dns)
- Se si utilizza l'identità federata, eseguire [la procedura seguente.](#federated-identity)

## <a name="applies-to-everyone"></a>Si applica a tutti gli utenti

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Prepararsi a informare gli utenti del riavvio e dell'accesso ai client dopo la migrazione. | Le licenze client di Office passano da Microsoft Cloud Deutschland ai servizi di Office 365 nella migrazione. I client prelevano una nuova licenza valida dopo la disconnessione e l'accesso ai client di Office. | I prodotti Office degli utenti devono aggiornare le licenze dai servizi di Office 365. Se le licenze non vengono aggiornate, i prodotti Office potrebbero verificarsi errori di convalida delle licenze. |
| Verificare la connettività di rete agli URL e agli indirizzi IP dei servizi [di Office 365.](https://aka.ms/o365urls) | Tutti i client e i servizi ospitati dal cliente che vengono utilizzati per accedere al servizio Office 365 devono essere in grado di accedere agli endpoint dei servizi globali di Office 365. <br>Nel caso in cui l'utente o i partner di collaborazione presentino regole firewall che impediscono l'accesso agli URL e agli indirizzi IP elencati negli URL e negli indirizzi IP dei servizi di [Office 365,](https://aka.ms/o365urls) è necessario modificare le regole del firewall per consentire l'accesso agli endpoint del servizio globale di Office 365| Se questa operazione non viene eseguita prima della fase 4, possono verificarsi errori del servizio o del software client  |
| Annullare eventuali sottoscrizioni di valutazione. | Le sottoscrizioni di valutazione non verranno migrate e blocteranno il trasferimento delle sottoscrizioni a pagamento. | I servizi di valutazione sono scaduti e non funzionanti se sono accessibili dagli utenti dopo l'annullamento. |
| Analizzare le differenze nelle funzionalità delle licenze tra Microsoft Cloud Deutschland e i servizi di Office 365. | I servizi di Office 365 includono funzionalità e servizi aggiuntivi non disponibili nell'attuale Microsoft Cloud Deutschland. Durante il trasferimento dell'abbonamento, le nuove funzionalità saranno disponibili per gli utenti. | <ul><li> Analizzare le diverse funzionalità fornite dalle licenze per Microsoft Cloud Deutschland e Office 365 Services. Iniziare con la descrizione del servizio della piattaforma [Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) </li><li> Determinare se le nuove funzionalità dei servizi di Office 365 devono essere inizialmente disabilitate per limitare gli effetti sugli utenti o sulla gestione delle modifiche degli utenti e modificare le assegnazioni delle licenze utente in base alle esigenze. </li><li>Preparare gli utenti e il personale dell'help desk per i nuovi servizi e funzionalità forniti dai servizi di Office 365. |
| Creare criteri di [conservazione a livello di organizzazione](https://docs.microsoft.com/microsoft-365/compliance/retention) per proteggere dall'eliminazione accidentale del contenuto durante la migrazione.  |<ul><li>Per assicurarsi che il contenuto non venga inavvertitamente eliminato dagli utenti finali durante la migrazione, i clienti possono scegliere di abilitare un criterio di conservazione a livello di organizzazione. </li><li>Anche se la conservazione non è necessaria, poiché i blocchi inseriti in qualsiasi momento durante la migrazione dovrebbero funzionare come previsto, disporre di un criterio di conservazione è un meccanismo di sicurezza di backup. Allo stesso tempo, un criterio di conservazione potrebbe non essere utilizzato da tutti i clienti, in particolare quelli che sono preoccupati per la conservazione.</li></ul>| Applicare i criteri di conservazione come descritto in [Informazioni sui criteri di conservazione e sulle etichette di conservazione.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) Se questa operazione non viene eseguita prima della fase 4 di 9, possono verificarsi errori del servizio o del software client. </li></ul>|
| Errori di licenza corretti | In alcuni casi, i clienti potrebbero essere in grado di utilizzare più servizi di quelli acquistati. Questa condizione è nota come sovravasto della licenza. Microsoft non è in grado di eseguire la migrazione dei clienti in condizioni di sovralicenza delle licenze da Microsoft Cloud Deutschland alle aree data center tedesche. Per garantire l'accesso continuo al servizio e ai dati, ogni utente assegnato richiede una licenza. | Tutti i clienti | I clienti devono valutare e risolvere la condizione di sovrassegnazione della licenza tramite l'acquisto di licenze aggiuntive o annullando l'assegnazione delle licenze da parte degli utenti. |
|||||

## <a name="active-directory-federation-services-ad-fs"></a>Active Directory Federation Services (ADFS)

**Si applica a**: I clienti che usano AD FS in locale per autenticare gli utenti che si connettono a Microsoft Office 365

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| [Backup della farm di Active Directory Federation Services (AD FS)](ms-cloud-germany-transition-add-adfs.md#backup) per scenari di ripristino di emergenza. | I clienti devono eseguire il backup della farm AD FS in modo appropriato per garantire che i trust della relying party agli endpoint globali di & Germany possano essere ripristinati senza toccare l'URI dell'autorità emittente dei domini. Microsoft consiglia di utilizzare ad FS Rapid Restore per un backup della farm e il rispettivo ripristino, se necessario. | Azione obbligatoria. L'inazione avrà un impatto sul servizio durante la migrazione se la farm AD FS del cliente ha esito negativo. Per ulteriori informazioni, vedere Passaggi [di migrazione adfs](https://docs.microsoft.com/microsoft-365/enterprise/ms-cloud-germany-transition-add-adfs) |
||||

## <a name="exchange-online"></a>Exchange Online

**Si applica a**: Clienti di Exchange Online che hanno abilitato la condivisione del calendario e dello spazio degli indirizzi di disponibilità.

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Informare i partner esterni della transizione imminente ai servizi di Office 365. | Le configurazioni dello spazio degli indirizzi di disponibilità consentono la condivisione delle informazioni sulla disponibilità con Office 365. | In caso negativo, potrebbe verificarsi un errore del servizio o del client in una fase successiva della migrazione dei clienti. |
|||||

### <a name="exchange-online-hybrid-configuration"></a>Configurazione ibrida di Exchange Online

**Si applica a**: Clienti di Exchange Online con una configurazione ibrida di Exchange attiva

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Eseguire l'aggiornamento alla versione più recente della procedura guidata di configurazione ibrida (HCW) ogni volta che il tenant entra nella fase di migrazione 5. È possibile avviare questa attività subito dopo aver ricevuto la notifica del Centro messaggi che indica che la migrazione del tenant di Office 365 è iniziata.<br><br> I clienti di Microsoft Cloud Deutschland ibridi di Exchange Online devono disinstallare le versioni precedenti di HCW, quindi installare ed eseguire la versione più recente (17.0.5378.0 o successiva) da [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) . |<ul><li>La versione più recente di HCW include gli aggiornamenti necessari per supportare i clienti che stanno transitando da Microsoft Cloud Deutschland ai servizi di Office 365.</li><li> Gli aggiornamenti includono modifiche alle impostazioni dei certificati locali per il connettore di invio e il connettore di ricezione.</li><li> Gli amministratori di Exchange devono installare di nuovo HCW in qualsiasi momento prima dell'inizio della fase 5 di 9 (migrazione di Exchange).<br>Quando si esegue HCW prima della fase 5, selezionare "Office 365 Germany" nella seconda pagina di HCW in _Office 365 Exchange Online_ nella casella di riepilogo sotto L'organizzazione di Office _365_ è ospitata da</li><li>**NOTA:** al termine della migrazione del tenant di Office 365, si rimuoverà e si installerà di nuovo HCW, questa volta utilizzando le impostazioni "Office 365 Worldwide" nella seconda pagina di HCW per completare la configurazione ibrida con il servizio globale Di Exchange Online.</li></ul>|La mancata esecuzione di HCW prima della fase 5 (migrazione di Exchange) può causare un errore del servizio o del client. |
||||

## <a name="sharepoint-online"></a>SharePoint Online

**Si applica a**: Clienti che utilizzano SharePoint 2013 locale


| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Limitare i flussi di lavoro di SharePoint 2013, da utilizzare durante la migrazione di SharePoint Online. | Ridurre i flussi di lavoro di SharePoint 2013 e completare i flussi di lavoro in-flight prima delle transizioni. | L'inazione può causare confusione dell'utente e chiamate all'help desk. |
||||

## <a name="skype-for-business-online"></a>Skype for Business Online

**Si applica a**: Clienti skype for business online

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Distribuire il client desktop di Teams per gli utenti che accedono a Skype for Business in Germania. | La migrazione sposta gli utenti di Skype for Business in Microsoft Teams per la collaborazione, le chiamate e le chat. Distribuire il client desktop di Microsoft Teams o verificare che sia disponibile un browser supportato. | L'inazione comporta l'inabilità dei servizi di collaborazione di Microsoft Teams. |
| Esaminare e preparare le modifiche DNS correlate alla migrazione. | Modifiche di zona DNS di proprietà del cliente per Skype for Business online. |<ul><li>È consigliabile aggiornare il time-to-live (TTL) per tutti i record DNS di dominio di proprietà del cliente a 5 minuti per accelerare l'aggiornamento dei record DNS. Tuttavia, il cutover gestito da Microsoft associato a questa modifica DNS può verificarsi in qualsiasi momento entro la finestra di modifica di 24 ore fornita. </li><li>L'interruzione del servizio è possibile in futuro. Gli utenti non potranno accedere a Skype for Business e verranno reindirizzati all'esperienza di Teams migrata nei servizi di Office 365. </li></ul>|
| Preparare la formazione e la preparazione per l'utente finale e l'amministrazione per la transizione a Microsoft Teams. | Avere successo nella transizione da Skype a Teams pianificando la comunicazione e la preparazione degli utenti. | <ul><li>I client devono essere a conoscenza dei nuovi servizi e delle modalità di utilizzo dopo la transizione dei servizi ai servizi di Office 365. </li><li>Dopo aver apportato modifiche al DNS sia per i domini di vanità dei clienti che per il dominio iniziale, gli utenti accederebbero a Skype for Business e vedevano che ora vengono migrati in Teams. In questo modo si scarica anche il client desktop per Teams in background. </li></ul>|
||||

## <a name="mobile"></a>Dispositivi mobili

Se si usa una soluzione mdm (Mobile Device Management) di terze parti:

| Step(s) | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Preparare la formazione per l'utente finale e l'amministrazione sugli utenti che rimuovono e aggiungono di nuovo il proprio account a Microsoft Outlook per iOS e Android. | Gli account di Microsoft Outlook per iOS e Android configurati con cassette postali in Microsoft Cloud Deutschland potrebbero essere rimossi e aggiunti di nuovo a Outlook per sincronizzare correttamente la nuova configurazione dei servizi di Office 365. | Clienti di Microsoft Outlook per iOS e Android | Le cassette postali di Outlook configurate in precedenza per Microsoft Cloud Deutschland potrebbero non riprendere la nuova configurazione dei servizi di Office 365, causando errori e peggiorando le prestazioni di altre esperienze utente. Gli amministratori IT sono invitati a fornire documentazione che istruisce in modo proattivo gli utenti a rimuovere e aggiungere di nuovo i propri account a Microsoft Outlook per iOS e Android se si verificano problemi con l'accesso o la sincronizzazione della posta dopo la migrazione. |
| Determinare se è necessaria una riconfigurazione dopo la migrazione. | Le soluzioni di gestione dei dispositivi mobili (MDM, Mobile Device Management) possono essere di destinazione `outlook.de` degli endpoint. In questa transizione ai servizi di Office 365, i profili client devono essere aggiornati all'URL dei servizi di Office 365, `outlook.office365.com` . | Clienti di Exchange Online e MDM | I client potrebbero continuare a funzionare mentre l'endpoint è accessibile, ma non riusciranno se `outlook.de` gli endpoint di Microsoft Cloud Deutschland non sono più disponibili. |
|||||

## <a name="line-of-business-apps"></a>App line-of-business

Se si usa un servizio di terze parti o app line-of-business integrate con Office 365: 

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Determinare se è necessaria una riconfigurazione dopo la migrazione. | I servizi e le applicazioni di terze parti che si integrano con Office 365 possono essere codificati per prevedere indirizzi IP e URL di Microsoft Cloud Deutschland. | Azione obbligatoria. L'inazione può causare errori del servizio o del software client. |
||||

## <a name="dynamics-365"></a>Dynamics 365

**Si applica a:** Clienti che usano Microsoft Dynamics

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Per le sottoscrizioni sandbox di Dynamics 365, assicurati di scaricare l'ambiente di produzione dell'istanza di Dynamics SQL dall'abbonamento Dynamics 365 in Microsoft Cloud Deutschland. Il backup di produzione più recente deve essere ripristinato nella sandbox prima della migrazione sandbox. | La migrazione di Dynamics 365 richiede ai clienti di verificare che l'ambiente sandbox sia aggiornato con il database di produzione più recente. | Il team di FastTrack assisterà i clienti nell'esecuzione di esecuzioni a secco per convalidare l'aggiornamento della versione da 8.x a 9.1.x. |
||||

## <a name="power-bi"></a>Power BI

**Si applica a**: Clienti di Power BI 

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Rimozione di oggetti dalle sottoscrizioni di Power BI che non verranno migrate da Power BI Microsoft Cloud Deutschland ai servizi di Office 365. | La migrazione dei servizi Power BI richiederà l'intervento del cliente per eliminare determinati elementi, ad esempio set di dati e dashboard. | <ul><li>Gli amministratori potrebbero essere necessario rimuovere gli elementi seguenti dalla sottoscrizione: </li><li>Real-Time set di dati (ad esempio, set di dati di streaming o push) </li><li>Origine dati e configurazione del gateway dati locale di Power BI </li></ul>|
||||

## <a name="dns"></a>DNS

**Si applica a:** Clienti che usano client desktop di Office (Microsoft 365 Apps, Office 365 ProPlus, Office 2019, 2016, ...)<br>
Rimuovere MSOID, CName dal DNS di proprietà del cliente, se esistente in qualsiasi momento prima del cut-over di Azure Active Directory (Azure AD). È possibile impostare un valore TTL di 5 minuti in modo che la modifica possa essere effettiva rapidamente.

## <a name="federated-identity"></a>Identità federativa

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Aggiungere un identificatore per single sign-on (SSO) a un trust relying party esistente e disabilitare gli aggiornamenti automatici dei metadati AD FS. | Prima di avviare la migrazione, è necessario aggiungere un ID all'attendibilità del componente ADFS. Per evitare la rimozione accidentale dell'identificatore del componente, disabilitare l'aggiornamento automatico per gli aggiornamenti dei metadati. <br><br> Eseguire questo comando come riga di comando singola nel server AD FS: <br>`Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:microsoftonline.de -Identifier @('urn:federation:microsoftonline.de', 'https://login.microsoftonline.de/extSTS.srf', 'https://login.microsoftonline.de') -AutoUpdate $False`
| Organizzazioni di autenticazione federata | Azione obbligatoria. L'inazione prima della fase 4 di 9 (SharePoint) avrà un impatto sul servizio durante la migrazione.  |
| Generare l'attendibilità della relying party per gli endpoint globali di Azure AD. | I clienti devono creare manualmente un trust relying party (RPT) per [gli](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) endpoint globali. A tale scopo, aggiungi un nuovo RPT tramite GUI sfruttando l'URL dei metadati della federazione globale e quindi usando le regole attestazione [RPT](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) di Azure AD (nella Guida di AD FS) per generare le regole attestazione e importarle in RPT. | Organizzazioni di autenticazione federata | Azione obbligatoria. L'inazione avrà un impatto sul servizio durante la migrazione. |
|||||

## <a name="microsoft-azure"></a>Microsoft Azure

Se si usa la stessa partizione di identità di Azure Active Directory per Office 365 e Microsoft Azure nell'istanza di Microsoft Cloud Deutschland, assicurarsi di prepararsi per la migrazione dei servizi di Microsoft Azure guidata dal cliente.
La migrazione dei servizi di Microsoft Azure non deve essere avviata prima che il tenant di Office 365 raggiunga la fase di migrazione 3 e deve essere completata prima del completamento della fase di migrazione 8.

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Determinare quali servizi di Azure sono in uso e prepararsi per la migrazione futura dalla Germania al tenant dei servizi di Office 365 collaborando con i partner. Seguire i passaggi descritti nel [playbook di migrazione di Azure](https://docs.microsoft.com/azure/germany/germany-migration-main). |<ul><li>La migrazione delle risorse di Azure è una responsabilità del cliente e richiede sforzi manuali seguendo i passaggi prescritti. La comprensione dei servizi in uso nell'organizzazione è fondamentale per la corretta migrazione dei servizi di Azure. </li><li> I clienti di Office 365 Germany che dispongono di sottoscrizioni di Azure nella stessa partizione di identità (organizzazione) devono seguire l'ordine prescritto da Microsoft quando possono iniziare la migrazione di sottoscrizione e servizi.</li></ul>|<ul><li>I clienti possono avere più sottoscrizioni di Azure, ogni sottoscrizione contenente infrastruttura, servizi e componenti della piattaforma. </li><li> Gli amministratori devono identificare le sottoscrizioni e le parti interessate per garantire che la migrazione e la convalida tempestive siano possibili nell'ambito di questo evento di migrazione. </li><li>Se non si riesce a completare correttamente la migrazione di queste sottoscrizioni e componenti di Azure entro la sequenza temporale prescritta, il completamento della transizione di Office e Azure AD ai servizi di Office 365 può causare la perdita di dati. </li><li> Una notifica del Centro messaggi segnalerà il punto in cui può iniziare la migrazione guidata dal cliente. </li></ul>|
||||

<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](https://docs.microsoft.com/azure/germany/germany-migration-main).

**Description:** Migration of Azure resources is a customer responsibility and requires manual effort following prescribed steps. Understanding what services are in use in the organization is key to successful migration of Azure services. 

Office 365 Germany customers who have Azure subscriptions under the same identity partition (organization) must follow the Microsoft-prescribed order when they can begin subscription and services migration.

**Applies to:** Azure Customers

**Impact:** 

- Customers may have multiple Azure subscriptions, each subscription containing infrastructure, services, and platform components. 
- Administrators should identify subscriptions and stakeholders to ensure prompt migration and validation is possible as part of this migration event.

  Failing to successfully complete migration of these subscriptions and Azure components within the prescribed timeline will affect completion of the Office and Azure AD transition to Office 365 services and may result in data loss.
- A Message center notification will signal the point at which customer-led migration can begin.
-->

## <a name="more-information"></a>Altre informazioni

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

- [Informazioni sul programma di migrazione di Dynamics 365](https://aka.ms/d365ceoptin)
- [Informazioni sul programma di migrazione di Power BI](https://aka.ms/pbioptin)
- [Guida introduttiva all'aggiornamento di Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
