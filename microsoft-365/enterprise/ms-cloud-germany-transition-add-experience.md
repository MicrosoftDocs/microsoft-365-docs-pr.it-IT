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
ms.openlocfilehash: 3f9bc40d7551dfcdb65abcf8b150f98b8242d7d2
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921691"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>Azioni e impatti delle fasi di migrazione per la migrazione da Microsoft Cloud Deutschland (avanzato) 

Le migrazioni dei tenant da Microsoft Cloud Deutschland all'area germania dei servizi di Office 365 di Microsoft vengono eseguite come set di fasi e le azioni configurate per ogni carico di lavoro. Questa figura mostra le nove fasi della migrazione ai nuovi datacenter tedeschi.

![Le nove fasi della migrazione ai nuovi datacenter tedeschi](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Le sezioni seguenti forniscono informazioni aggiuntive sulle esperienze dei clienti quando si esegue il passaggio da Microsoft Cloud Germania (Microsoft Cloud Deutschland) ai servizi di Office 365 nella nuova area data center tedesca.

## <a name="services"></a>Servizi

### <a name="azure-ad-phase-2-of-9"></a>Azure AD (fase 2 di 9)

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Tenant di Azure AD in Microsoft Cloud Deutschland copiato nei servizi di Office 365. | Azure AD copia il tenant nei servizi di Office 365. Gli identificatori del tenant e dell'utente vengono mantenuti. Le chiamate al servizio Azure AD vengono reindirizzate da Microsoft Cloud Deutschland ai servizi di Office 365 e sono trasparenti per i servizi. | Tutti i clienti di Office | - Le richieste DSR (Data Subject Requests) del Regolamento generale sulla protezione dei dati (GDPR) vengono eseguite dal portale di amministrazione di Azure per le richieste future. Tutti i dati di diagnostica legacy o non dei clienti residenti in Microsoft Cloud Deutschland vengono eliminati entro 30 giorni. <br><br> - I clienti che utilizzano le autenticazioni federate con Active Directory Federation Services (AD FS) non devono apportare modifiche agli URI dell'autorità emittente utilizzati per tutte le autenticazioni con Active Directory locale durante la migrazione. La modifica degli URI dell'autorità emittente causa errori di autenticazione per gli utenti nel dominio. Gli URI dell'autorità emittente possono essere modificati direttamente  in AD FS o quando un dominio viene convertito da gestito a _federato_ e viceversa. È consigliabile non aggiungere, rimuovere o convertire un dominio federato nel tenant di Azure AD di cui è stata eseguita la migrazione. Gli URI dell'autorità emittente possono essere modificati al termine della migrazione. <br><br> - Le richieste di autenticazione a più fattori (MFA) che usano Microsoft Authenticator vengono visualizzate come ID oggetto utente (un GUID) mentre il tenant viene copiato nei servizi di Office 365. Le richieste MFA verranno eseguite come previsto nonostante questo comportamento di visualizzazione.  Gli account Microsoft Authenticator attivati tramite gli endpoint dei servizi di Office 365 visualizzano il nome dell'entità utente (UPN).  Gli account aggiunti tramite gli endpoint di Microsoft Cloud Deutschland visualizzano l'OBJECTID dell'utente, ma funzioneranno sia con gli endpoint dei servizi di Microsoft Cloud Deutschland che con gli endpoint dei servizi di Office 365.  |
| Stabilire AuthServer in locale che punti al servizio token di sicurezza globale. | Ciò garantisce che le richieste degli utenti che eseguono la migrazione a Microsoft Cloud Deutschland per le richieste di disponibilità di Exchange per l'ambiente ibrido locale siano autenticate per accedere al servizio locale. In modo analogo, questo garantirà l'autenticazione delle richieste dagli endpoint dei servizi locali a Office 365. | Clienti di Exchange Online con distribuzioni ibride (locali) | Al termine della migrazione di Azure AD, l'amministratore della topologia di Exchange (ibrida) locale deve aggiungere un nuovo endpoint del servizio di autenticazione per i servizi di Office 365. Con questo comando da Exchange PowerShell, sostituire `<TenantID>` con l'ID tenant dell'organizzazione (disponibile nel portale di Azure in **Azure Active Directory).** <br><br> - `New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> Se non si completa questa attività, le richieste di disponibilità ibride potrebbero non fornire informazioni agli utenti delle cassette postali migrati da Microsoft Cloud Deutschland ai servizi di Office 365.  |
| Migrazione delle risorse di Azure. | I clienti che usano le risorse di Office 365 e Azure (ad esempio, rete, calcolo e archiviazione) eseguiranno la migrazione delle risorse all'istanza dei servizi di Office 365. Questa migrazione è responsabilità dei clienti. I post del Centro messaggi segnaleranno l'inizio. La migrazione deve essere completata prima della finalizzazione dell'organizzazione di Azure AD nell'ambiente dei servizi di Office 365. | Clienti di Azure | Per le migrazioni di Azure, vedere il playbook sulla migrazione di Azure, [Panoramica delle indicazioni sulla migrazione per Azure Germania.](https://docs.microsoft.com/azure/germany/germany-migration-main) |
|||||

### <a name="exchange-online-phase-5-of-9"></a>Exchange Online (fase 5 di 9)

Se si usa **Set-UserPhoto:**

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| La nuova area geografica germania viene aggiunta a una configurazione dell'organizzazione esistente e le cassette postali vengono spostate nei servizi di Office 365. | La configurazione di Exchange Online aggiunge la nuova area tedesca go-local all'organizzazione di transizione. Questa area dei servizi di Office 365 è impostata come predefinita, che consente al servizio di bilanciamento del carico interno di ridistribuire le cassette postali nell'area predefinita appropriata nei servizi di Office 365. In questa transizione, gli utenti su entrambi i lati (germania o servizi di Office 365) sono nella stessa organizzazione e possono usare entrambi gli endpoint URL. |  Exchange Online | Se è stata eseguita la migrazione di una cassetta postale utente ma non è stata eseguita la migrazione di una cassetta postale dell'amministratore o viceversa, gli amministratori non potranno eseguire **Set-UserPhoto**, un cmdlet di PowerShell. In questo caso, un amministratore deve passare una stringa aggiuntiva durante la configurazione della connessione `ConnectionUri` utilizzando la sintassi seguente: <br><br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br><br> dove è il segnaposto per l'ID e-mail dell'utente la cui foto deve `<user_email>` essere modificata tramite **Set-UserPhoto.** |
|||||

Se si utilizza una distribuzione ibrida locale:

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
|Interrompere o eliminare qualsiasi spostamento onboarding o offboarding delle cassette postali.  | In questo modo le richieste di spostamento non hanno esito negativo con un errore. | Clienti di Exchange Online con distribuzioni ibride (locali) | Azione obbligatoria. In caso negativo, potrebbe verificarsi un errore del servizio o dei client software. |
|||||

### <a name="dynamics-phase-8-of-9"></a>Dynamics (fase 8 di 9)

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Risorse di Microsoft Dynamics | I clienti con Microsoft Dynamics saranno impegnati da Progettazione o FastTrack per la transizione di Dynamics all'istanza dei servizi di Office 365.* | Clienti di Microsoft Dynamics 365 | - Dopo la migrazione, l'amministratore convalida l'organizzazione. <br><br> - L'amministratore modifica i flussi di lavoro, se necessario. <br><br> - L'amministratore cancella la modalità AdminOnly in base alle esigenze. <br><br> - L'amministratore modifica il tipo di organizzazione _da Sandbox,_ in base alle esigenze <br><br> - Notificare agli utenti finali il nuovo URL per accedere all'istanza (organizzazione). <br><br> - Aggiornare tutte le connessioni in ingresso al nuovo URL dell'endpoint. <br><br> - Il servizio Dynamics non sarà disponibile per gli utenti durante la transizione. <br><br> - Gli utenti devono convalidare l'integrità e le funzionalità dell'organizzazione dopo la migrazione di ogni organizzazione.  |
|||||

\* (i) I clienti con Microsoft Dynamics 365 devono intervenire in questo scenario di migrazione, come definito dal processo di migrazione fornito. (ii) Se il cliente non riesce a eseguire un'azione, Microsoft non sarà in grado di completare la migrazione. (iii) Quando Microsoft non è in grado di completare la migrazione a causa dell'inazione del cliente, la sottoscrizione del cliente scadrà il 29 ottobre 2021. 


### <a name="power-bi-phase-8-of-9"></a>Power BI (fase 8 di 9)

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Migrazione delle risorse di Power BI | I clienti con Microsoft Power BI verranno coinvolti da Progettazione o FastTrack dopo aver attivato manualmente uno strumento di migrazione PBI esistente per eseguire la transizione di Power BI all'istanza dei servizi di Office 365.\*\* | Clienti di Microsoft Power BI | - Gli elementi di Power BI seguenti _non verranno_ esportati e doranno essere ri-creati: <br><br> - Set di dati in tempo reale (ad esempio set di dati di streaming o push). <br> - Configurazione e origine dati del gateway dati locale di Power BI. <br> - I report creati in base ai set di dati in tempo reale non saranno disponibili dopo la migrazione e devono essere ricreati. <br><br> - I servizi Power BI non saranno disponibili per gli utenti durante la transizione. L'inabilità del servizio non deve essere superiore a 24 ore. <br><br> - Gli utenti doranno riconfigurare le origini dati e i gateway dati locali con il servizio Power BI dopo la migrazione.  Fino a quando non viene eseguita questa operazione, gli utenti non saranno in grado di utilizzare queste origini dati per eseguire l'aggiornamento pianificato e/o indirizzare le query su tali origini dati. <br><br> - Non è possibile eseguire la migrazione delle capacità e delle aree di lavoro premium. I clienti devono eliminare tutte le capacità prima della migrazione e crearle di nuovo dopo la migrazione. Spostare di nuovo le aree di lavoro nelle capacità desiderate.  |
|||||

\*\* (i) I clienti con Microsoft Power BI devono intervenire in questo scenario di migrazione, come definito dal processo di migrazione fornito. (ii) Se il cliente non riesce a eseguire un'azione, Microsoft non sarà in grado di completare la migrazione. (iii) Quando Microsoft non è in grado di completare la migrazione a causa dell'inazione del cliente, la sottoscrizione del cliente scadrà il 29 ottobre 2021. 


### <a name="office-apps-phase-9-of-9"></a>App di Office (fase 9 di 9)

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Client, Office Online durante il cutover del client Office, Azure AD finalizza l'ambito tenant in modo che punti ai servizi di Office 365. | Questa modifica alla configurazione consente ai client di Office di eseguire l'aggiornamento e puntare agli endpoint dei servizi di Office 365. | Tutti i clienti di Office | - Informare gli utenti di chiudere tutte le app di _Office_ e quindi accedere nuovamente (o forzare il riavvio dei client e gli utenti ad accedere) per consentire ai client di Office di raccogliere la modifica. <br><br> - Notificare agli utenti  e al personale dell'help desk che gli utenti potrebbero visualizzare un banner di Office che chiede loro di riattivare le app di Office entro 72 ore dal passaggio completo. <br><br> - Tutte le applicazioni di Office nei computer personali devono essere chiuse e gli utenti devono disconnettersi e quindi accedere di nuovo. Nella barra di attivazione gialla, accedere per riattivare i servizi di Office 365. <br><br> - I computer condivisi richiederanno azioni simili ai computer personali e non richiederanno una procedura speciale. <br><br> - Nei dispositivi mobili, gli utenti devono disconnettersi dall'app, chiuderle e quindi accedere di nuovo. |
|||||

## <a name="during-migration"></a>Durante la migrazione

### <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (fase 4 di 9)

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| La transizione di SharePoint e OneDrive è in fase di transizione. | SharePoint e OneDrive vengono migrati da Microsoft Cloud Deutschland ai servizi di Office 365 in questa fase. Gli URL esistenti di Microsoft Cloud Deutschland vengono mantenuti ( `contoso.sharepoint.de` ). I token emessi dai servizi Microsoft Cloud Deutschland o Office 365 sono validi durante la transizione. | Clienti di SharePoint | I flussi di lavoro di SharePoint 2013 verranno interrotti durante la migrazione e devono essere ripubblicati dopo la migrazione. |
|||||


### <a name="exchange-online-phase-5-of-9"></a>Exchange Online (fase 5 di 9)

Per eDiscovery:

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Durante la migrazione, le ricerche eDiscovery avranno esito negativo o restituiranno 0 risultati per i percorsi di SharePoint Online, OneDrive for Business ed Exchange Online migrati. | Durante la migrazione, i clienti possono continuare a creare casi, blocchi, ricerche ed esportazioni nel Centro [sicurezza & conformità,](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)inclusa [la ricerca di contenuto.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)  Tuttavia, le ricerche nei percorsi di SharePoint Online, OneDrive for Business ed Exchange Online migrati restituiranno 0 risultati o genereranno un errore. Per la correzione, vedere la _colonna_ Impatto. | Tutti i clienti che utilizzano eDiscovery |  Nel caso in cui una ricerca restituisca 0 risultati o un errore durante la migrazione, eseguire l'azione seguente per SharePoint Online: <br><br>  Scaricare i siti direttamente dal sito di SharePoint Online/ OneDrive for Business seguendo le istruzioni in Scaricare file e cartelle [da OneDrive o SharePoint.](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05) Questo metodo richiede autorizzazioni di amministratore di SharePoint Online o autorizzazioni di sola lettura per il sito. <br><br> Se vengono superati i limiti, come illustrato in Scaricare file e cartelle da OneDrive o [SharePoint,](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)i clienti possono usare il client di sincronizzazione di OneDrive for Business seguendo le indicazioni in Sincronizzare i file di SharePoint e Teams con il [computer.](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88) <br><br> - Exchange Online <br><br> - [eDiscovery sul posto in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
|||||


### <a name="skype-for-business-online-phase-7-of-9"></a>Skype for Business online (fase 7 di 9)

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Migrazione di Skype for Business a Teams. | I clienti Skype for Business esistenti vengono migrati ai servizi di Office 365 in Europa e quindi vengono migrati a Microsoft Teams nell'area germania dei servizi di Office 365. | Clienti Skype for Business |  PowerShell verrà utilizzato per amministrare le impostazioni e i criteri per il tenant e gli utenti. Quando ci si connette a una sessione di PowerShell, aggiungere quanto segue: <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"` |
|||||


## <a name="post-migration"></a>Dopo la migrazione

### <a name="azure-ad-phase-9-of-9"></a>Azure AD (fase 9 di 9)

Per ambienti ibridi:

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Aggiornare Azure AD Connect. | Al termine del processo di migrazione ad Azure AD, l'organizzazione usa completamente i servizi di Office 365 e non è più connessa a Microsoft Cloud Deutschland. A questo punto, il cliente deve verificare che il processo di sincronizzazione delta sia stato finalizzato e successivamente modificare il valore stringa da `AzureInstance` 3 (Microsoft Cloud Deutschland) a 0 nel percorso del Registro di `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` sistema. | Organizzazioni ibride connesse ad Azure AD | Modificare il valore di `AzureInstance` , la chiave del Registro di sistema. In caso contrario, gli oggetti non verranno sincronizzati dopo che gli endpoint di Microsoft Cloud Deutschland non saranno più disponibili. |
|||||

Per l'autenticazione federata:

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Rimuovere le relazioni di trust della relying party da Microsoft Cloud Deutschland AD FS. | Al termine del processo di migrazione ad Azure AD, l'organizzazione usa completamente i servizi di Office 365 e non è più connessa a Microsoft Cloud Deutschland. A questo punto, il cliente deve rimuovere l'attendibilità della relying party per gli endpoint di Microsoft Cloud Deutschland. Questa operazione può essere eseguita solo quando nessuna applicazione del cliente punta agli endpoint di Microsoft Cloud Deutschland quando Azure AD viene utilizzato come provider di identità (IdP). | Organizzazioni con autenticazione federata | Nessuna. |
|||||

Per Azure AD:

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Le richieste di aggiunta a un gruppo di Azure AD negli ultimi 30 giorni prima della migrazione dovranno essere nuovamente richieste se la richiesta originale non è stata approvata. | I clienti degli utenti finali dovranno usare il pannello Di accesso per inviare di nuovo la richiesta di partecipazione a un gruppo di Azure AD se tali richieste non sono state approvate negli ultimi 30 giorni prima della migrazione. | Utenti finali le cui richieste di approvazione del gruppo di Azure AD non sono state approvate negli ultimi 30 giorni prima della migrazione |  Come utente finale: <ol><li>Passare al [pannello Di accesso.](https://account.activedirectory.windowsazure.com/r#/joinGroups)</li><li>Trovare un gruppo di Azure AD per il quale l'approvazione dell'appartenenza era in sospeso entro 30 giorni prima della migrazione.</li><li>Richiedi di aggiungere di nuovo il gruppo di Azure AD.</li></ol> Le richieste di partecipazione a un gruppo attive meno di 30 giorni prima della migrazione non possono essere approvate, a meno che non vengano richieste nuovamente dopo la migrazione. |
|||||

Per DNS:

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Aggiornare i servizi DNS locali per gli endpoint dei servizi di Office 365. | Le voci DNS gestite dal cliente che puntano a Office 365 Germany devono essere aggiornate per puntare agli endpoint dei servizi di Office 365. | Tutti i clienti di Office | Azione obbligatoria. In caso negativo, potrebbe verificarsi un errore del servizio o dei client software. |
|||||

Per i servizi di terze parti per gli endpoint dei servizi di Office 365:

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Aggiornare i partner e i servizi di terze parti per gli endpoint dei servizi di Office 365. | - I servizi e i partner di terze parti che puntano a Office 365 Germany devono essere aggiornati per puntare agli endpoint dei servizi di Office 365. Esempio: registrare nuovamente, in linea con i fornitori e i partner, la versione delle applicazioni della raccolta, se disponibile. <br><br> - Puntare tutte le applicazioni personalizzate che sfruttano l'API Graph `graph.microsoft.de` da `graph.microsoft.com` a . Anche altre API con endpoint modificati devono essere aggiornate, se sfruttate. <br><br> - Modificare tutte le applicazioni aziendali non di prima parte in modo che reindirizzano agli endpoint globali.  | Tutti i clienti di Office | Azione obbligatoria. In caso negativo, potrebbe verificarsi un errore del servizio o dei client software. |
|||||

### <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (fase 4 di 9)

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Ripubblicare i flussi di lavoro di SharePoint 2013. | Nel lavoro di pre-migrazione è stato ridotto il numero di flussi di lavoro di SharePoint 2013. Al termine della migrazione, il cliente può ripubblicare i flussi di lavoro. | Tutti i clienti di Office | Si tratta di un'azione obbligatoria. In caso negativo, potrebbero verificarsi confusione per l'utente e le chiamate al supporto tecnico. |
| Condividere elementi tramite Outlook | La condivisione degli elementi tramite Outlook non funziona più dopo il cutover del tenant. | SharePoint Online e OneDrive for Business | - In SharePoint Online e OneDrive for Business, è possibile condividere elementi tramite Outlook. Dopo aver premuto il pulsante di Outlook, viene creato un collegamento condivisibile che viene inserito in un nuovo messaggio in Outlook Web App. <br><br> - Dopo il cutover del tenant, questo metodo di condivisione non funzionerà. Riconosciamo che si tratta di un problema noto. Tuttavia, poiché questa funzionalità di Outlook è nel percorso della deprecazione, la correzione del problema non è pianificata fino all'implementazione della deprecazione. |


### <a name="exchange-online-phase-5-of-9"></a>Exchange Online (fase 5 di 9)

Se si utilizza una configurazione ibrida di Exchange:

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Eseguire di nuovo la procedura guidata di configurazione ibrida (HCW) nei servizi di Office 365. | La configurazione HCW esistente è destinata a supportare Microsoft Cloud Deutschland. Una volta completata la migrazione dei servizi di Exchange, la configurazione locale viene disaccodata da Microsoft Cloud Deutschland. | Clienti di Exchange Online che eseguono una distribuzione ibrida | - Azione obbligatoria. In caso negativo, potrebbe verificarsi un errore del servizio o dei client software. Prima che inizi la migrazione delle cassette postali di Exchange (con 5 o più giorni di preavviso), informare i client che devono interrompere ed eliminare eventuali spostamenti di onboarding o offboarding delle proprie cassette postali.  In caso contrario, verranno visualizzati errori nelle richieste di spostamento. <br><br> - Al termine della migrazione delle cassette postali di Exchange, informare i client che possono riprendere gli spostamenti di onboarding e offboarding. <br> **L'esecuzione di Test-MigrationServerAvailabiilty**, un cmdlet di PowerShell, durante la migrazione di Exchange da Microsoft Cloud Deutschland ai servizi di Office 365 potrebbe non funzionare. Tuttavia, funzionerà correttamente al termine della migrazione. <br><br> Se si verificano problemi con le credenziali o l'autorizzazione dei client dopo la migrazione delle cassette postali, gli utenti possono reimmigare le credenziali di amministratore locale nell'endpoint di migrazione eseguendo oppure impostando la stessa impostazione utilizzando il Pannello di controllo `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` di Exchange.  |

Per eDiscovery:

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
