---
title: Azioni e impatti delle fasi di migrazione per la migrazione da Microsoft Cloud Deutschland (avanzato)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
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
description: "Riepilogo: informazioni aggiuntive sull'esperienza del cliente durante il passaggio da Microsoft Cloud Germania (Microsoft Cloud Deutschland) ai servizi di Office 365 nella nuova area data center tedesca."
ms.openlocfilehash: b38ed865306eb676c8f57c1dcbb4541fae43c8df
ms.sourcegitcommit: 9adb89206daa075af34a73bcb7e8fb86d7c2919a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2021
ms.locfileid: "50603997"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>Azioni e impatti delle fasi di migrazione per la migrazione da Microsoft Cloud Deutschland (avanzato) 

Le migrazioni dei tenant da Microsoft Cloud Deutschland all'area germania dei servizi di Office 365 di Microsoft vengono eseguite come set di fasi e le azioni configurate per ogni carico di lavoro. Questa figura mostra le nove fasi della migrazione ai nuovi datacenter tedeschi.

![Le nove fasi della migrazione ai nuovi datacenter della Germania](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Le sezioni seguenti forniscono informazioni aggiuntive sulle esperienze dei clienti quando si esegue il passaggio da Microsoft Cloud Germania (Microsoft Cloud Deutschland) ai servizi di Office 365 nella nuova area data center tedesca.

## <a name="office-365-portal-services"></a>Servizi portale di Office 365

Tra la fase 2 di 9 e la fase 3 di 9, il portale per i partner potrebbe non essere accessibile. Durante questo periodo, il partner potrebbe non essere in grado di accedere alle informazioni sui tenant nel portale per i partner. Poiché ogni migrazione è diversa, la durata dell'accessibilità può essere in ore.

### <a name="prework-for-azure-ad-phase-2"></a>Lavoro preliminare per Azure AD (fase 2)

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Tenant di Azure AD in Microsoft Cloud Deutschland copiato nei servizi di Office 365. | Azure AD copia il tenant nei servizi di Office 365. Gli identificatori del tenant e dell'utente vengono mantenuti. Le chiamate al servizio Azure AD vengono reindirizzate da Microsoft Cloud Deutschland ai servizi di Office 365 e sono trasparenti per i servizi. | Tutti i clienti di Office | - Le richieste DSR (Data Subject Requests) del Regolamento generale sulla protezione dei dati (GDPR) vengono eseguite dal portale di amministrazione di Azure per le richieste future. Tutti i dati di diagnostica legacy o non dei clienti residenti in Microsoft Cloud Deutschland vengono eliminati entro 30 giorni. <br><br> - I clienti che utilizzano le autenticazioni federate con Active Directory Federation Services (AD FS) non devono apportare modifiche agli URI dell'autorità emittente utilizzati per tutte le autenticazioni con Active Directory locale durante la migrazione. La modifica degli URI dell'autorità emittente causa errori di autenticazione per gli utenti nel dominio. Gli URI dell'autorità emittente possono essere modificati direttamente  in AD FS o quando un dominio viene convertito da gestito a _federato_ e viceversa. È consigliabile non aggiungere, rimuovere o convertire un dominio federato nel tenant di Azure AD di cui è stata eseguita la migrazione. Gli URI dell'autorità emittente possono essere modificati al termine della migrazione. <br><br> - Le richieste di autenticazione a più fattori (MFA) che usano Microsoft Authenticator vengono visualizzate come ID oggetto utente (un GUID) mentre il tenant viene copiato nei servizi di Office 365. Le richieste MFA verranno eseguite come previsto nonostante questo comportamento di visualizzazione.  Gli account Microsoft Authenticator attivati tramite gli endpoint dei servizi di Office 365 visualizzano il nome dell'entità utente (UPN).  Gli account aggiunti tramite gli endpoint di Microsoft Cloud Deutschland visualizzano l'ObjectID dell'utente, ma funzioneranno con entrambi gli endpoint dei servizi di Microsoft Cloud Deutschland e Office 365.  |
| Migrazione delle risorse di Azure. | I clienti che usano le risorse di Office 365 e Azure (ad esempio, rete, calcolo e archiviazione) eseguiranno la migrazione delle risorse all'istanza dei servizi di Office 365. Questa migrazione è responsabilità dei clienti. I post del Centro messaggi segnaleranno l'inizio. La migrazione deve essere completata prima della finalizzazione dell'organizzazione di Azure AD nell'ambiente dei servizi di Office 365. | Clienti di Azure | Per le migrazioni di Azure, vedere il playbook sulla migrazione di Azure, [Panoramica delle indicazioni sulla migrazione per Azure Germania.](https://docs.microsoft.com/azure/germany/germany-migration-main) |
|||||

### <a name="exchange-online-before-phase-5"></a>Exchange Online prima della fase 5

**Si applica a:** Tutti i clienti che utilizzano una configurazione ibrida di Exchange con i server Exchange in locale

| Passaggi | Descrizione | Impatto |
|:-------|:-------|:-------|
| Stabilire che AuthServer in locale punti al servizio token di sicurezza globale. | Ciò garantisce che le richieste degli utenti che eseguono la migrazione a Microsoft Cloud Deutschland per le richieste di disponibilità di Exchange per l'ambiente ibrido locale siano autenticate per accedere al servizio locale. Analogamente, questo garantirà l'autenticazione delle richieste dall'ambiente locale agli endpoint dei servizi di Office 365. | Al termine della migrazione di Azure AD, l'amministratore della topologia di Exchange (ibrida) locale deve aggiungere un nuovo endpoint del servizio di autenticazione per i servizi di Office 365. Con questo comando da Exchange PowerShell, sostituire `<TenantID>` con l'ID tenant dell'organizzazione (disponibile nel portale di Azure in **Azure Active Directory).**<br><br>`New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> Se non si completa questa attività, le richieste di disponibilità ibride potrebbero non fornire informazioni agli utenti delle cassette postali migrati da Microsoft Cloud Deutschland ai servizi di Office 365.  |
|Interrompere o eliminare gli spostamenti delle cassette postali di onboarding o offboarding, in modo da non spostare le cassette postali tra Exchange locale ed Exchange Online  | In questo modo le richieste di spostamento delle cassette postali non hanno esito negativo con un errore. | In caso negativo, potrebbe verificarsi un errore del servizio o dei client software. |
||||

<!--
    Question from ckinder
    Not clear if this has to be done before, during or after phase 5
-->

**Si applica a:** Tutti i clienti che archiviano le foto degli utenti in Exchange Online e usano **Set-UserPhoto:**

| Passaggi | Descrizione | Impatto |
|:-------|:-------|:-------|
| La nuova area geografica "Germania" viene aggiunta alla configurazione di un'organizzazione di Exchange Online esistente e le cassette postali vengono spostate nei servizi di Office 365. | La configurazione di Exchange Online aggiunge la nuova area tedesca go-local all'organizzazione di transizione. Questa area dei servizi di Office 365 è impostata come predefinita, che consente al servizio di bilanciamento del carico interno di ridistribuire le cassette postali nell'area predefinita appropriata nei servizi di Office 365. In questa transizione, gli utenti su entrambi i lati (germania o servizi di Office 365) sono nella stessa organizzazione e possono usare entrambi gli endpoint URL. | Se è stata eseguita la migrazione di una cassetta postale utente ma non è stata eseguita la migrazione di una cassetta postale dell'amministratore o viceversa, gli amministratori non potranno eseguire **Set-UserPhoto**, un cmdlet di PowerShell. In questo caso, un amministratore deve passare una stringa aggiuntiva durante la configurazione della connessione `ConnectionUri` utilizzando la sintassi seguente: <br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br> dove è il segnaposto per l'ID di posta elettronica dell'utente la cui foto deve `<user_email>` essere modificata tramite **Set-UserPhoto.** |
||||

## <a name="during-migration"></a>Durante la migrazione

### <a name="sharepoint-online-phase-4"></a>Fase 4 di SharePoint Online

**Si applica a:** Tutti i clienti che utilizzano eDiscovery

| Passaggi | Descrizione | Impatto |
|:-------|:-------|:-------|
| La transizione di SharePoint e OneDrive è in fase di transizione. | SharePoint e OneDrive vengono migrati da Microsoft Cloud Deutschland ai servizi globali di Office 365 nella fase 4. Gli URL esistenti di Microsoft Cloud Deutschland vengono mantenuti ( `contoso.sharepoint.de` ). I token emessi dai servizi Microsoft Cloud Deutschland o Office 365 sono validi durante la transizione. | I flussi di lavoro di SharePoint 2013 verranno interrotti durante la migrazione e devono essere ripubblicati dopo la migrazione. |
||||

### <a name="ediscovery-phase-4-to-the-end-of-phase-9"></a>Fase 4 di eDiscovery alla fine della fase 9

**Si applica a:** Tutti i clienti che utilizzano eDiscovery

| Passaggi | Descrizione | Impatto |
|:-------|:-------|:-------|
| Dal completamento della fase 4 fino alla fase 9, le ricerche eDiscovery avranno esito negativo o restituiranno 0 risultati per i percorsi di SharePoint Online, OneDrive for Business ed Exchange Online migrati. | Durante la migrazione, i clienti possono continuare a creare casi, blocchi, ricerche ed esportazioni nel Centro [sicurezza & conformità,](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)inclusa [la ricerca di contenuto.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)  Tuttavia, le ricerche nei percorsi di SharePoint Online, OneDrive for Business ed Exchange Online migrati restituiranno 0 risultati o genereranno un errore. Per la correzione, vedere la _colonna_ Impatto. | Nel caso in cui una ricerca restituisca zero risultati o un errore durante la migrazione, eseguire l'azione seguente per SharePoint Online: <ul><li>Scaricare i siti direttamente dal sito di SharePoint Online/ OneDrive for Business seguendo le istruzioni in Scaricare file e cartelle [da OneDrive o SharePoint.](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05) Questo metodo richiede autorizzazioni di amministratore di SharePoint Online o autorizzazioni di sola lettura per il sito.</li><li>Se vengono superati i limiti, come illustrato in Scaricare file e cartelle da OneDrive o [SharePoint,](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)i clienti possono usare il client di sincronizzazione di OneDrive for Business seguendo le indicazioni in Sincronizzare i file di SharePoint e Teams con il [computer.](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)</li><li>Per ulteriori informazioni, vedere  [eDiscovery sul posto in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
||||

## <a name="post-migration"></a>Dopo la migrazione

### <a name="azure-ad-phase-9"></a>Fase 9 di Azure AD

**Si applica a:** Tutti i clienti che sincronizzano le identità con Azure AD Connect

| Passaggi | Descrizione | Impatto |
|:-------|:-------|:-------|
| Aggiornare Azure AD Connect. | Al termine del processo di migrazione ad Azure AD, l'organizzazione usa completamente i servizi di Office 365 e non è più connessa a Microsoft Cloud Deutschland. A questo punto, il cliente deve verificare che il processo di sincronizzazione delta sia stato finalizzato e successivamente modificare il valore stringa da `AzureInstance` 3 (Microsoft Cloud Deutschland) a 0 nel percorso del Registro di `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` sistema. | Modificare il valore di `AzureInstance` , la chiave del Registro di sistema. In caso contrario, gli oggetti non verranno sincronizzati dopo che gli endpoint di Microsoft Cloud Deutschland non saranno più disponibili. |
|||||

**Si applica a:** Tutti i clienti che utilizzano l'autenticazione federata con ADFS

| Passaggi | Descrizione | Impatto |
|:-------|:-------|:-------|
| Rimuovere le relazioni di trust della relying party da Microsoft Cloud Deutschland AD FS. | Al termine del processo di migrazione ad Azure AD, l'organizzazione usa completamente i servizi di Office 365 e non è più connessa a Microsoft Cloud Deutschland. A questo punto, il cliente deve rimuovere l'attendibilità della relying party per gli endpoint di Microsoft Cloud Deutschland. Questa operazione può essere eseguita solo quando nessuna applicazione del cliente punta agli endpoint di Microsoft Cloud Deutschland quando Azure AD viene utilizzato come provider di identità (IdP). | Organizzazioni con autenticazione federata | Nessuna. |
|||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
Per Azure AD:

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Le richieste di aggiunta a un gruppo di Azure AD negli ultimi 30 giorni prima della migrazione dovranno essere nuovamente richieste se la richiesta originale non è stata approvata. | I clienti degli utenti finali dovranno usare il pannello Di accesso per inviare di nuovo la richiesta di partecipazione a un gruppo di Azure AD se tali richieste non sono state approvate negli ultimi 30 giorni prima della migrazione. | Utenti finali le cui richieste di approvazione del gruppo di Azure AD non sono state approvate negli ultimi 30 giorni prima della migrazione |  Come utente finale: <ol><li>Passare al [pannello Accesso.](https://account.activedirectory.windowsazure.com/r#/joinGroups)</li><li>Trovare un gruppo di Azure AD per il quale l'approvazione dell'appartenenza era in sospeso entro 30 giorni prima della migrazione.</li><li>Richiedi di aggiungere di nuovo il gruppo di Azure AD.</li></ol> Le richieste di partecipazione a un gruppo attive meno di 30 giorni prima della migrazione non possono essere approvate, a meno che non vengano richieste nuovamente dopo la migrazione. |
|||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
**Si applica a:**  Tutti i clienti che gestiscono le proprie zone DNS

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Aggiornare i servizi DNS locali per gli endpoint dei servizi di Office 365. | Le voci DNS gestite dal cliente che puntano a Microsoft Cloud Deutschland devono essere aggiornate in modo da puntare agli endpoint dei servizi globali di Office 365. | In caso negativo, potrebbe verificarsi un errore del servizio o dei client software. |
||||

Per i servizi di terze parti per gli endpoint dei servizi di Office 365:

| Passaggi | Descrizione | Impatto |
|:-------|:-------|:-------|
| Aggiornare i partner e i servizi di terze parti per gli endpoint dei servizi di Office 365. | <ul><li>I servizi e i partner di terze parti che puntano a Office 365 Germany devono essere aggiornati per puntare agli endpoint dei servizi di Office 365. Esempio: registra di nuovo, in linea con i tuoi fornitori e partner, la versione delle applicazioni della raccolta, se disponibile. </li><li>Puntare tutte le applicazioni personalizzate che sfruttano l'API Graph `graph.microsoft.de` da `graph.microsoft.com` a . Anche altre API con endpoint modificati devono essere aggiornate, se sfruttate. </li><li>Modificare tutte le applicazioni aziendali non di prima parte in modo che reindirizzano agli endpoint globali. </li></ul>| Azione obbligatoria. In caso negativo, potrebbe verificarsi un errore del servizio o dei client software. |
||||

### <a name="sharepoint-online-post-migration"></a>Post-migrazione di SharePoint Online

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Ripubblicare i flussi di lavoro di SharePoint 2013. | Nel lavoro di pre-migrazione è stato ridotto il numero di flussi di lavoro di SharePoint 2013. Al termine della migrazione, il cliente può ripubblicare i flussi di lavoro. | Si tratta di un'azione obbligatoria. In caso negativo, potrebbero verificarsi confusione per l'utente e le chiamate all'help desk. |
| Condividere elementi tramite Outlook | La condivisione di elementi in SharePoint Online e OneDrive for Business tramite Outlook non funziona più dopo il cutover del tenant. |<ul><li>In SharePoint Online e OneDrive for Business, è possibile condividere elementi tramite Outlook. Dopo aver premuto il pulsante di Outlook, viene creato un collegamento condivisibile che viene inserito in un nuovo messaggio in Outlook Web App.</li><li>Dopo il cutover del tenant, questo metodo di condivisione non funzionerà. Riconosciamo che si tratta di un problema noto. Tuttavia, poiché questa funzionalità di Outlook è nel percorso della deprecazione, la correzione del problema non è pianificata fino all'implementazione della deprecazione. </li></ul>|
||||

### <a name="exchange-online-post-migration"></a>Post-migrazione di Exchange Online

Se si utilizza una configurazione ibrida di Exchange:

| Passaggi | Descrizione | Impatto |
|:-------|:-------|:-------|
| Eseguire di nuovo la procedura guidata di configurazione ibrida (HCW) nei servizi di Office 365. | La configurazione HCW esistente è destinata a supportare Microsoft Cloud Deutschland. Una volta completata la migrazione dei servizi di Exchange, la configurazione locale viene disaccouplata da Microsoft Cloud Deutschland. |<ul><li>Azione obbligatoria. In caso negativo, potrebbe verificarsi un errore del servizio o dei client software. Prima dell'inizio della migrazione delle cassette postali di Exchange (con 5 o più giorni di preavviso), informare i client che devono interrompere ed eliminare eventuali spostamenti di onboarding o offboarding delle cassette postali.  In caso contrario, verranno visualizzati errori nelle richieste di spostamento. </li><li>Al termine della migrazione delle cassette postali di Exchange, informare i client che possono riprendere gli spostamenti di onboarding e offboarding. <br> L'esecuzione di **Test-MigrationServerAvailabiilty**, un cmdlet di PowerShell, durante la migrazione di Exchange da Microsoft Cloud Deutschland ai servizi di Office 365 potrebbe non funzionare. Tuttavia, funzionerà correttamente al termine della migrazione. </li><li>Se si verificano problemi con le credenziali o l'autorizzazione dei client dopo la migrazione delle cassette postali, gli utenti possono reimmigare le credenziali di amministratore locale nell'endpoint di migrazione eseguendo oppure impostando la stessa impostazione utilizzando il Pannello di controllo di `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` Exchange. </li></ul>|

### <a name="ediscovery-post-migration"></a>Post-migrazione di eDiscovery

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
|  Tutte le posizioni di SharePoint Online, OneDrive for Business ed Exchange Online sono state migrate insieme al Centro sicurezza e conformità (SCC). | Tutte le attività di eDiscovery devono essere eseguite dal tenant internazionale. Le ricerche avranno ora esito positivo al 100%.  Eventuali errori o errori devono seguire i normali canali di supporto. | Tutti i clienti che utilizzano eDiscovery | Nessuna. |
| Rimuovere i criteri di conservazione a livello di organizzazione creati durante i passaggi di pre-migrazione | I clienti possono rimuovere i criteri di conservazione a livello di organizzazione creati durante il lavoro di pre-migrazione dei clienti. | Tutti i clienti che hanno applicato un criterio di conservazione come parte dei passaggi di pre-migrazione. | Nessuna. |
|||||

## <a name="next-step"></a>Passaggio successivo

[Comprendere le azioni e gli impatti delle fasi di migrazione](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Ulteriori informazioni

Guida introduttiva:

- [Migrazione da Microsoft Cloud Deutschland ai servizi di Office 365 nelle nuove aree data center tedesche](ms-cloud-germany-transition.md)
- [Assistenza per la migrazione di Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Come acconsentire esplicitamente a eseguire la migrazione](ms-cloud-germany-migration-opt-in.md)
- [Esperienza del cliente durante la migrazione](ms-cloud-germany-transition-experience.md)

Spostamento attraverso la transizione:

- [Azioni ed impatti sulle fasi della migrazione](ms-cloud-germany-transition-phases.md)
- [Pre-lavoro aggiuntivo](ms-cloud-germany-transition-add-pre-work.md)
- Ulteriori informazioni per [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivi,](ms-cloud-germany-transition-add-devices.md) [esperienze](ms-cloud-germany-transition-add-experience.md)e [AD FS.](ms-cloud-germany-transition-add-adfs.md)

App cloud:

- [Informazioni sul programma di migrazione di Dynamics 365](https://aka.ms/d365ceoptin)
- [Informazioni sul programma di migrazione di Power BI](https://aka.ms/pbioptin)
- [Guida introduttiva all'aggiornamento di Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
