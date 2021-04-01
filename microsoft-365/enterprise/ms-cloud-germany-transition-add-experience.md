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
ms.openlocfilehash: 8e28b9d6c8cc23e128234973039a4873b327e9fd
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476375"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>Azioni e impatti delle fasi di migrazione per la migrazione da Microsoft Cloud Deutschland (avanzato)

Le migrazioni dei tenant da Microsoft Cloud Deutschland all'area germania dei servizi di Office 365 di Microsoft vengono eseguite come set di fasi e le azioni configurate per ogni carico di lavoro. Questa figura mostra le dieci fasi della migrazione ai nuovi datacenter tedeschi.

![Le dieci fasi della migrazione ai nuovi datacenter tedeschi](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Nelle sezioni seguenti vengono fornite ulteriori informazioni sulle esperienze dei clienti quando si esegue il passaggio da Microsoft Cloud Germania (Microsoft Cloud Deutschland) ai servizi di Office 365 nella nuova area data center tedesca.

## <a name="office-365-portal-services-between-phase-2-and-phase-3"></a>Servizi portale di Office 365 tra la fase 2 e la fase 3

Tra la fase 2 e la fase 3, partner Portal potrebbe non essere accessibile. Durante questo periodo, il partner potrebbe non essere in grado di accedere alle informazioni del tenant nel portale per i partner. Poiché ogni migrazione è diversa, la durata dell'accessibilità può essere in ore.

### <a name="ediscovery-phase-4-to-the-end-of-phase-9"></a>Fase 4 di eDiscovery alla fine della fase 9

**Si applica a:** Tutti i clienti che utilizzano eDiscovery

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Dall'inizio della fase 4 fino al completamento della fase 9, le ricerche eDiscovery avranno esito negativo o restituiranno 0 risultati per i percorsi di SharePoint Online, OneDrive for Business ed Exchange Online migrati. | Durante la migrazione, i clienti possono continuare a creare casi, blocchi, ricerche ed esportazioni nel [Centro sicurezza & conformità,](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)inclusa [ricerca contenuto.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content) Tuttavia, le ricerche nei percorsi di SharePoint Online, OneDrive for Business ed Exchange Online di cui è stata eseguita la migrazione restituiranno 0 risultati o genereranno un errore. Per la correzione, vedere la _colonna_ Impatto. | Nel caso in cui una ricerca restituisca zero risultati o un errore durante la migrazione, eseguire l'azione seguente per SharePoint Online: <ul><li>Scaricare i siti direttamente dal sito di SharePoint Online o OneDrive for Business seguendo le istruzioni in Scaricare file e cartelle [da OneDrive o SharePoint.](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05) Questo metodo richiede autorizzazioni di amministratore di SharePoint Online o autorizzazioni di sola lettura per il sito.</li><li>Se vengono superati i limiti, come illustrato in Scaricare file e cartelle da OneDrive o [SharePoint,](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)i clienti possono utilizzare il client di sincronizzazione di OneDrive for Business seguendo le indicazioni in Sincronizzare i file di SharePoint e Teams con il [computer.](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)</li><li>Per ulteriori informazioni, vedere  [eDiscovery sul posto in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
||||

## <a name="exchange-online-set-userphoto-during-phase-5"></a>Exchange Online Set-UserPhoto durante la fase 5

**Si applica a:** Tutti i clienti che archiviano le foto degli utenti in Exchange Online e utilizzano **Set-UserPhoto**:

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| La nuova area geografica "Germania" viene aggiunta a una configurazione dell'organizzazione di Exchange Online esistente e le cassette postali vengono spostate nei servizi di Office 365. | La configurazione di Exchange Online aggiunge la nuova area tedesca locale all'organizzazione di transizione. Questa area dei servizi di Office 365 è impostata come predefinita, che consente al servizio di bilanciamento del carico interno di ridistribuire le cassette postali nell'area predefinita appropriata nei servizi di Office 365. In questa transizione, gli utenti su entrambi i lati (germania o servizi di Office 365) sono nella stessa organizzazione e possono usare entrambi gli endpoint URL. | Se è stata eseguita la migrazione di una cassetta postale utente ma non è stata eseguita la migrazione di una cassetta postale di amministratore o viceversa, gli amministratori non saranno in grado di eseguire **Set-UserPhoto**, un cmdlet di PowerShell. In questo caso, un amministratore deve passare una stringa aggiuntiva durante la configurazione della connessione `ConnectionUri` utilizzando la sintassi seguente: <br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br> dove è il segnaposto per l'ID di posta elettronica dell'utente la cui foto deve `<user_email>` essere modificata utilizzando **Set-UserPhoto**. |
||||

## <a name="post-migration"></a>Dopo la migrazione

### <a name="azure-ad-phase-9"></a>Fase 9 di Azure AD

**Si applica a:** Tutti i clienti che sincronizzano le identità con Azure AD connect

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Aggiornare Azure AD Connect. | Una volta completato il cut over ad Azure AD, l'organizzazione usa completamente i servizi di Office 365 e non è più connessa a Microsoft Cloud Deutschland. A questo punto, il cliente deve assicurarsi che il processo di sincronizzazione delta sia stato finalizzato e, successivamente, modificare il valore stringa di `AzureInstance` da 3 (Microsoft Cloud Deutschland) a 0 nel percorso del Registro di `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` sistema. | Modificare il valore di `AzureInstance` , la chiave del Registro di sistema. In caso contrario, gli oggetti non verranno sincronizzati dopo che gli endpoint di Microsoft Cloud Deutschland non saranno più disponibili. |
|||||

**Si applica a:** Tutti i clienti che utilizzano l'autenticazione federata con ADFS

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Rimuovere attendibilità relying party da Microsoft Cloud Deutschland AD FS. | Al termine del cut-over ad Azure AD, l'organizzazione usa completamente i servizi di Office 365 e non è più connessa a Microsoft Cloud Deutschland. A questo punto, il cliente deve rimuovere l'attendibilità del relying party per gli endpoint di Microsoft Cloud Deutschland. Questa operazione può essere eseguita solo quando nessuna delle applicazioni del cliente punta agli endpoint di Microsoft Cloud Deutschland quando Azure AD viene utilizzato come provider di identità (IdP). | Organizzazioni con autenticazione federata | Nessuna. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
**Si applica a:** Utenti finali le cui richieste di approvazione di gruppo di Azure AD non sono state approvate negli ultimi 30 giorni prima della migrazione 

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Le richieste di partecipazione a un gruppo di Azure AD negli ultimi 30 giorni prima della migrazione dovranno essere nuovamente richieste se la richiesta originale non è stata approvata. | Se tali richieste non sono state approvate negli ultimi 30 giorni prima della migrazione, i clienti dell'utente finale dovranno usare il pannello di accesso per inviare di nuovo una richiesta di partecipazione a un gruppo di Azure AD. |  Come utente finale: <ol><li>Passare a [Pannello di accesso](https://account.activedirectory.windowsazure.com/r#/joinGroups).</li><li>Trovare un gruppo di Azure AD per il quale l'approvazione dell'appartenenza era in sospeso durante i 30 giorni precedenti la migrazione.</li><li>Richiedere di aggiungere di nuovo il gruppo di Azure AD.</li></ol> Le richieste di partecipazione a un gruppo attivo meno di 30 giorni prima della migrazione non possono essere approvate, a meno che non vengano richieste di nuovo dopo la migrazione. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
**Si applica a:**  Tutti i clienti che gestiscono le proprie zone DNS

| Step(s) | Descrizione | Impatto |
|:------|:-------|:-------|
| Aggiornare i servizi DNS locali per gli endpoint dei servizi di Office 365. | Le voci DNS gestite dal cliente che puntano a Microsoft Cloud Deutschland devono essere aggiornate per puntare agli endpoint dei servizi globali di Office 365. | L'esito negativo di questa operazione può causare un errore del servizio o dei client software. |
||||

**Si applica a:** Clienti che usano servizi di terze parti per gli endpoint dei servizi di Office 365

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Aggiornare i partner e i servizi di terze parti per gli endpoint dei servizi di Office 365. | <ul><li>I servizi di terze parti e i partner che puntano a Office 365 Germany devono essere aggiornati per puntare agli endpoint dei servizi di Office 365. Esempio: registrare di nuovo, in linea con i fornitori e i partner, la versione dell'app raccolta delle applicazioni, se disponibile. </li><li>Puntare tutte le applicazioni personalizzate che sfruttano l'API Graph da `graph.microsoft.de` a `graph.microsoft.com` . Anche altre API con endpoint modificati devono essere aggiornate, se sfruttate. </li><li>Modificare tutte le applicazioni aziendali non di prima parte in modo che reindirizzano agli endpoint globali. </li></ul>| Azione obbligatoria. L'esito negativo di questa operazione può causare un errore del servizio o dei client software. |
||||

### <a name="sharepoint-online-post-migration"></a>Post-migrazione di SharePoint Online

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Ripubblicare i flussi di lavoro di SharePoint 2013. | Nel lavoro di pre-migrazione, è stato ridotto il numero di flussi di lavoro di SharePoint 2013. Al termine della migrazione, il cliente può ripubblicare i flussi di lavoro. | Si tratta di un'azione obbligatoria. La mancata operazione può causare confusione per l'utente e le chiamate all'help desk. |
| Condividere elementi tramite Outlook | La condivisione di elementi in SharePoint Online e OneDrive for Business tramite Outlook non funziona più dopo il cutover del tenant. |<ul><li>In SharePoint Online e OneDrive for Business, è possibile condividere elementi tramite Outlook. Dopo aver premuto il pulsante di Outlook, viene creato un collegamento condivisibile e inserito in un nuovo messaggio in Outlook Web App.</li><li>Dopo il cutover del tenant, questo metodo di condivisione non funzionerà. Riconosciamo che si tratta di un problema noto. Tuttavia, poiché questa funzionalità di Outlook è nel percorso della deprecazione, la correzione del problema non è pianificata fino a quando non viene implementazione della deprecazione. </li></ul>|
||||

### <a name="exchange-online-post-migration"></a>Exchange Online dopo la migrazione

Se si utilizza una configurazione ibrida di Exchange:

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Eseguire di nuovo la procedura guidata di configurazione ibrida (HCW) nei servizi di Office 365. | La configurazione HCW esistente è destinata a supportare Microsoft Cloud Deutschland. Al termine della migrazione dei servizi di Exchange, la configurazione locale viene disaccodata da Microsoft Cloud Deutschland. |<ul><li>Azione obbligatoria. L'esito negativo di questa operazione può causare un errore del servizio o dei client software. Prima dell'inizio della migrazione delle cassette postali di Exchange (con 5 o più giorni di preavviso), informare i client che devono interrompere ed eliminare eventuali spostamenti di onboarding o offboarding delle proprie cassette postali.  In caso contrario, verranno visualizzati errori nelle richieste di spostamento. </li><li>Al termine della migrazione delle cassette postali di Exchange, informare i client che possono riprendere l'onboarding e gli spostamenti di offboarding. <br> **L'esecuzione di Test-MigrationServerAvailabiilty**, un cmdlet di PowerShell, durante la migrazione di Exchange da Microsoft Cloud Deutschland ai servizi di Office 365 potrebbe non funzionare. Tuttavia, funzionerà correttamente al termine della migrazione. </li><li>Se i client si verificano problemi con le credenziali o l'autorizzazione dopo la migrazione delle cassette postali, gli utenti possono reim annotarsi le proprie credenziali di amministratore locale nell'endpoint di migrazione eseguendo o impostando lo stesso utilizzando il Pannello di controllo `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` di Exchange. </li></ul>|

### <a name="ediscovery-post-migration"></a>Post-migrazione di eDiscovery

**Si applica a:** Tutti i clienti che utilizzano eDiscovery

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
|  Tutte le posizioni di SharePoint Online, OneDrive for Business ed Exchange Online sono state migrate insieme al Centro sicurezza e conformità (SCC). | Tutte le attività di eDiscovery devono essere eseguite dal tenant globale. Le ricerche avranno ora esito positivo al 100%.  Eventuali errori o errori devono seguire i normali canali di supporto. | Nessuno |
||||

**Si applica a:**  Tutti i clienti che hanno applicato un criterio di conservazione nell'ambito della procedura di pre-migrazione

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Rimuovere i criteri di conservazione a livello di organizzazione creati durante la procedura di pre-migrazione | I clienti possono rimuovere i criteri di conservazione a livello di organizzazione creati durante le attività di pre-migrazione dei clienti. | Nessuno |
||||

## <a name="next-step"></a>Passaggio successivo

[Comprendere le azioni e gli impatti delle fasi di migrazione](ms-cloud-germany-transition-phases.md)

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