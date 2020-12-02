---
title: Ulteriori informazioni sull'esperienza per la migrazione da Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
description: "Riepilogo: ulteriori informazioni sull'esperienza dei clienti quando si passa da Microsoft Cloud Germany (Microsoft Cloud Deutschland) a servizi di Office 365 nella nuova area datacenter tedesca."
ms.openlocfilehash: b282a12966e7a6dc8a1a331409834322c5087a10
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551876"
---
# <a name="additional-experience-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Ulteriori informazioni sull'esperienza per la migrazione da Microsoft Cloud Deutschland 

Nelle sezioni seguenti vengono fornite ulteriori informazioni sulle esperienze dei clienti.

## <a name="services"></a>Servizi

### <a name="azure-ad"></a>Azure AD

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Il tenant di Azure AD in Microsoft Cloud Deutschland è stato copiato nei servizi di Office 365. | Azure AD copia il tenant in Office 365 Services. Gli identificatori tenant e User vengono mantenuti. Le chiamate al servizio di Azure AD vengono reindirizzate da Microsoft Cloud Deutschland ai servizi di Office 365 e sono trasparenti ai servizi. | Tutti i clienti di Office | -Informazioni generali sulla protezione dei dati (GDPR) le richieste del soggetto dei dati (richieste DSR) vengono eseguite dal portale di amministrazione di Azure per le richieste future. Tutti i dati di diagnostica legacy o non clienti che risiedono in Microsoft Cloud Deutschland vengono eliminati entro e non oltre i 30 giorni. <br><br> -I clienti che utilizzano le autenticazioni federate con Active Directory Federation Services (AD FS) non devono apportare modifiche agli URI degli emittenti utilizzati per tutte le autenticazioni con Active Directory locale durante la migrazione. La modifica degli URI degli emittenti comporterà errori di autenticazione per gli utenti del dominio. Gli URI dell'autorità emittente possono essere modificati direttamente in AD FS o quando un dominio viene convertito da _gestito_ a _federato_ e viceversa. È consigliabile che i clienti non aggiungano, rimuovano o convertano un dominio federato nel tenant di Azure AD di cui è stata eseguita la migrazione. Gli URI dell'autorità emittente possono essere modificati dopo che la migrazione è stata completata completamente. <br><br> -Richieste di autenticazione a più fattori (AMF) che utilizzano Microsoft Authenticator come utente ObjectID (GUID) mentre il tenant viene copiato nei servizi di Office 365. Le richieste dell'AMF si esibiranno come previsto nonostante questo comportamento di visualizzazione.  Gli account Microsoft Authenticator che sono stati attivati tramite gli endpoint dei servizi di Office 365 visualizzano il nome dell'entità utente (UPN).  Gli account aggiunti tramite gli endpoint di Microsoft Cloud Deutschland visualizzeranno l'utente ObjectID, ma lavoreranno con gli endpoint di Microsoft Cloud Deutschland e Office 365 Services.  |
| Stabilire AuthServer locale che punta al servizio STS globale. | In questo modo si garantisce che le richieste provenienti da utenti che eseguono la migrazione a Microsoft Cloud Deutschland per richieste di disponibilità di Exchange destinate all'ambiente ibrido locale vengano autenticate per accedere al servizio locale. Analogamente, questo assicurerà l'autenticazione delle richieste da locali agli endpoint dei servizi di Office 365. | Clienti di Exchange Online con distribuzioni ibride (locali) | Al termine della migrazione di Azure AD, l'amministratore della topologia di Exchange locale (ibrida) deve aggiungere un nuovo endpoint del servizio di autenticazione per i servizi di Office 365. Con questo comando di Exchange PowerShell, sostituire `<TenantID>` con l'ID tenant dell'organizzazione (trovato nel portale di Azure in **Azure Active Directory**). <br><br> - `New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> La mancata esecuzione di questa attività può comportare la mancata esecuzione di richieste di disponibilità ibride per gli utenti di cassette postali di cui è stata eseguita la migrazione da Microsoft Cloud Deutschland ai servizi di Office 365.  |
| Migrazione delle risorse di Azure. | I clienti che utilizzano le risorse di Office 365 e Azure (ad esempio, la rete, il computo e l'archiviazione) eseguono la migrazione delle risorse all'istanza di servizi di Office 365. Questa migrazione è una responsabilità per i clienti. I post del centro messaggi segnalano l'inizio. La migrazione deve essere completata prima della finalizzazione dell'organizzazione di Azure AD nell'ambiente dei servizi di Office 365. | Clienti di Azure | Per le migrazioni di Azure, vedere l'articolo relativo alla migrazione di Azure, [Panoramica delle linee guida per la migrazione di Azure Germany](https://docs.microsoft.com/azure/germany/germany-migration-main). |
|||||

<!--
[Reference: Experience][Data Protection] Experience][
[Reference: Experience][Federation] 
[Reference: Experience][MFA]  


[Reference: Experience – Post Migration][Hybrid]    
        

[Reference: Experience – During Migration] [Azure] 
-->

### <a name="exchange-online"></a>Exchange Online

Se si sta utilizzando **Set-UserPhoto**:

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| La nuova area di Germania viene aggiunta a una configurazione dell'organizzazione esistente e le cassette postali vengono spostate in servizi di Office 365. | La configurazione di Exchange Online aggiunge la nuova area tedesca di go-local all'organizzazione di transizione. Questa area di servizi di Office 365 è impostata come predefinita, consentendo al servizio di bilanciamento del carico interno di ridistribuire le cassette postali nell'area predefinita appropriata in Office 365 Services. In questa transizione, gli utenti di entrambi i lati (Germania o Office 365 Services) si trovano nella stessa organizzazione e possono utilizzare l'endpoint URL. |  Exchange Online | Se è stata eseguita la migrazione di una cassetta postale dell'utente, ma non è stata eseguita la migrazione di una cassetta postale dell'amministratore o viceversa, gli amministratori non saranno in grado di eseguire **Set-UserPhoto**, un cmdlet di PowerShell. In questo caso, un amministratore deve passare una stringa aggiuntiva `ConnectionUri` durante la connessione configurata utilizzando la sintassi seguente: <br><br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br><br> dove `<user_email>` è il segnaposto per l'ID di posta elettronica dell'utente di cui è necessario modificare la foto utilizzando **Set-UserPhoto**. |
|||||

<!--
[Reference: Experience][Exchange Online]  [if using Set-UserPhoto] 
-->  

Se si utilizza una distribuzione ibrida locale:

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
|Interrompere o eliminare eventuali spostamenti onboarding o offboarding delle cassette postali.  | In questo modo le richieste di spostamento non avranno esito negativo con un errore. | Clienti di Exchange Online con distribuzioni ibride (locali) | Azione obbligatoria. La mancata applicazione può causare un errore del servizio o dei client software. |
|||||

<!--
[Reference: Experience][Hybrid] 
--> 


### <a name="dynamics"></a>Dynamics

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Risorse di Microsoft Dynamics | I clienti con Microsoft Dynamics saranno impegnati in Engineering o FastTrack per la transizione alla dinamica all'istanza di servizi di Office 365. * | Clienti di Microsoft Dynamics 365 | -Dopo la migrazione, l'amministratore convalida l'organizzazione. <br><br> -L'amministratore modifica i flussi di lavoro, in base alle esigenze. <br><br> -L'amministratore Annulla la modalità AdminOnly in base alle esigenze. <br><br> -L'amministratore cambia il tipo di organizzazione dalla _sandbox_, a seconda dei casi <br><br> -Informare gli utenti finali del nuovo URL per accedere all'istanza (org). <br><br> -Aggiornare tutte le connessioni in ingresso al nuovo URL dell'endpoint. <br><br> -Il servizio Dynamics non sarà disponibile per gli utenti durante la transizione. <br><br> -Gli utenti sono tenuti a convalidare l'integrità dell'organizzazione e le caratteristiche dopo la migrazione di ogni organizzazione organizzativa.  |
|||||

\* (i) i clienti con Microsoft Dynamics 365 devono intervenire in questo scenario di migrazione, come definito dal processo di migrazione fornito. (II) la mancata esecuzione da parte del cliente comporterà che Microsoft non sarà in grado di completare la migrazione. (III) quando Microsoft non è in grado di completare la migrazione a causa dell'inattività del cliente, la sottoscrizione del cliente scadrà il 29 ottobre 2021. 


### <a name="power-bi"></a>Power BI

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Migrazione delle risorse di Power BI | I clienti con Microsoft Power BI saranno impegnati in Engineering o FastTrack dopo l'attivazione manuale di uno strumento di migrazione di PBI esistente per la transizione di Power BI all'istanza di servizi di Office 365.\*\* | Clienti di Microsoft Power BI | -I seguenti elementi Power BI _non_ verranno transizione e dovranno essere ricreati: <br><br> -Set di DataSet in tempo reale, ad esempio flussi o set di DataSet di tipo push. <br> -Power BI in locale-configurazione del gateway di dati e origine dati. <br> -I rapporti creati al di sopra dei set di informazioni in tempo reale non saranno disponibili dopo la migrazione e devono essere ricreati. <br><br> -I servizi Power BI non saranno disponibili per gli utenti durante la transizione. L'indisponibilità del servizio non dovrebbe essere superiore a 24 ore. <br><br> -Gli utenti saranno tenuti a riconfigurare le origini dati e i relativi gateway di dati locali con il servizio Power BI dopo la migrazione.  Fino a quando non lo faranno, gli utenti non saranno in grado di utilizzare queste origini dati per eseguire l'aggiornamento pianificato e/o le query dirette su queste origini dati. <br><br> -Non è possibile eseguire la migrazione delle capacità e delle aree di lavoro avanzate. I clienti devono eliminare tutte le capacità prima della migrazione e ricrearle dopo la migrazione. Spostare le aree di lavoro di nuovo a capacità come desiderato.  |
|||||

\*\* (i) i clienti con Microsoft Power BI devono intervenire in questo scenario di migrazione, come definito dal processo di migrazione fornito. (II) la mancata esecuzione da parte del cliente comporterà che Microsoft non sarà in grado di completare la migrazione. (III) quando Microsoft non è in grado di completare la migrazione a causa dell'inattività del cliente, la sottoscrizione del cliente scadrà il 29 ottobre 2021. 


### <a name="office-apps"></a>App di Office

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Client, Office Online durante Office client completa, Azure AD consente di completare l'ambito tenant in modo che puntino ai servizi di Office 365.<!--v-gmoor: What?--> | Questa modifica di configurazione consente ai client di Office di eseguire l'aggiornamento e di puntare agli endpoint dei servizi di Office 365. | Tutti i clienti di Office | -Rimuovere MSOID CName da DNS di proprietà del cliente, se esiste. <br><br> -Avvisare gli utenti di chiudere _tutte_ le app di Office e quindi di riaccedere (o forzare il riavvio dei client e gli utenti a accedere) per consentire ai client di Office di ritirare la modifica. <br><br> -Informare gli utenti e il personale del supporto tecnico che gli utenti *possono* visualizzare un banner di Office che richiede loro di riattivare le app di office entro 72 ore dall'completa. <br><br> -Tutte le applicazioni di Office nei computer personali devono essere chiuse e gli utenti devono disconnettersi e quindi eseguire di nuovo l'accesso. Nella barra di attivazione gialla, accedere per riattivare i servizi di Office 365. <br><br> -I computer condivisi richiedono operazioni simili a quelle dei computer personali e non richiedono una procedura speciale. <br><br> -Su dispositivi mobili, gli utenti devono disconnettersi dalle app, chiuderli e quindi eseguire nuovamente l'accesso. |
|||||

<!--
[Reference: Experience][Office Apps]
--> 

## <a name="during-migration"></a>Durante la migrazione


### <a name="exchange-online"></a>Exchange Online

Per eDiscovery:

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Durante la migrazione, le ricerche di eDiscovery avranno esito negativo o restituiranno 0 Risultati per SharePoint Online, OneDrive for business e i percorsi di Exchange Online che sono stati migrati. | Durante la migrazione, i clienti possono continuare a creare casi, esenzioni, ricerche ed esportazioni nel centro sicurezza & conformità, inclusa la ricerca contenuto.  Tuttavia, le ricerche eseguite su SharePoint Online, OneDrive for business e sui percorsi di Exchange Online di cui è stata eseguita la migrazione restituiranno 0 risultati o genereranno un errore. Per la correzione, vedere la colonna _impatto_ . | Tutti i clienti che utilizzano eDiscovery |  Nel caso in cui una ricerca restituisca 0 risultati o un errore durante la migrazione, eseguire la procedura seguente per SharePoint Online: <br><br>  Scaricare siti direttamente dal sito di SharePoint Online/OneDrive for business attenendosi alle istruzioni riportate in [download di file e cartelle da OneDrive o SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05). Questo metodo richiede autorizzazioni di amministratore di SharePoint Online o autorizzazioni di sola lettura per il sito. <br><br> Se vengono superati i limiti, come spiegato in [download di file e cartelle da OneDrive o SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05), i clienti possono utilizzare il client di sincronizzazione di OneDrive for business seguendo le indicazioni riportate in [Sync SharePoint and Teams files with your computer](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88). <br><br> -Exchange Online <br><br> - [EDiscovery sul posto in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
|||||

<!--
[Reference: Experience – During Migration][ [eDiscovery]
-->          


### <a name="sharepoint-online"></a>SharePoint Online

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| SharePoint e OneDrive vengono transizione. | SharePoint e OneDrive vengono migrati da Microsoft Cloud Deutschland a Office 365 Services in questa fase. Gli URL esistenti di Microsoft Cloud Deutschland sono conservati ( `contoso.sharepoint.de` ). I token emessi da Microsoft Cloud Deutschland o Office 365 Services sono validi durante la transizione. | Clienti di SharePoint | I flussi di lavoro di SharePoint 2013 Inflight verranno interrotti durante la migrazione e dovranno essere ripubblicati dopo la migrazione. |
|||||

<!--
[Reference: Experience – During Migration][ [SPO]
-->  

### <a name="skype-for-business-online"></a>Skype for Business Online

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Migrazione di Skype for business a teams. | I clienti Skype for business esistenti vengono migrati nei servizi di Office 365 in Europa e quindi trasferiti a Microsoft teams nell'area Germania dei servizi di Office 365. | Clienti Skype for business |  PowerShell utilizzerà per amministrare le impostazioni e i criteri per il tenant e gli utenti. Quando si esegue la connessione a una sessione di PowerShell, aggiungere quanto segue: <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"` |
|||||

<!--
[Reference: Experience – During Migration][ [SfBO]
-->  


## <a name="post-migration"></a>Dopo la migrazione

### <a name="azure-ad"></a>Azure AD

Per l'ambiente ibrido:

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Aggiornamento di Azure AD Connect. | Dopo aver completato il taglio su Azure AD, l'organizzazione utilizza completamente i servizi di Office 365 e non è più connessa a Microsoft Cloud Deutschland. A questo punto, il cliente deve garantire che il processo di sincronizzazione Delta sia stato completato e, successivamente, modificare il valore stringa `AzureInstance` da 3 (Microsoft Cloud Deutschland) su 0 nel percorso del registro di sistema `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` . | Organizzazioni ibride AD Azure AD-Connected | Modificare il valore della `AzureInstance` chiave del registro di sistema. In caso contrario, gli oggetti non verranno sincronizzati dopo che gli endpoint di Microsoft Cloud Deutschland non sono più disponibili. |
|||||

<!--
[Reference: Experience – Post Migration][Hybrid]
--> 

Per l'autenticazione federata:

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Rimuovere i trust di relying party da Microsoft Cloud Deutschland AD FS. | Dopo aver completato il taglio su Azure AD, l'organizzazione utilizza completamente i servizi di Office 365 e non è più connessa a Microsoft Cloud Deutschland. A questo punto, il cliente deve rimuovere la relazione di trust relying party negli endpoint di Microsoft Cloud Deutschland. Questa operazione può essere fatta solo quando nessuna applicazione del cliente punta a endpoint di Microsoft Cloud Deutschland quando Azure AD viene sfruttato come un provider di identità (IdP). | Organizzazioni di autenticazione federata | Nessuna. |
|||||

<!--
[Reference: Experience – Post Migration][Federated]
-->             

Per Azure AD:

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Le richieste di partecipazione a un gruppo di Azure AD negli ultimi 30 giorni prima della migrazione dovranno essere richieste nuovamente se la richiesta originale non è stata approvata. | I clienti degli utenti finali dovranno utilizzare il pannello di accesso per inviare di nuovo la richiesta di partecipazione a un gruppo di Azure AD se tali richieste non sono state approvate negli ultimi 30 giorni prima della migrazione. | Utenti finali le cui richieste di approvazione del gruppo Azure AD non sono state approvate negli ultimi 30 giorni prima della migrazione |  Come utente finale: <ol><li>Passare a [Pannello di accesso](https://account.activedirectory.windowsazure.com/r#/joinGroups).</li><li>Individuare un gruppo di Azure AD per il quale l'approvazione di appartenenza è stata sospesa in 30 giorni prima della migrazione.</li><li>Richiedere di nuovo l'aggiunta al gruppo di Azure AD.</li></ol> Richieste di partecipazione a un gruppo attivo meno di 30 giorni prima che la migrazione non venga approvata, a meno che non vengano ririchieste dopo la migrazione. |
|||||

<!--
[Reference: Experience – Post Migration][Azure AD]
--> 

Per DNS:

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Aggiornare i servizi DNS locali per gli endpoint dei servizi di Office 365. | Le voci DNS gestite dal cliente che puntano a Office 365 Germany devono essere aggiornate in modo che puntino agli endpoint dei servizi di Office 365. | Tutti i clienti di Office | Azione obbligatoria. La mancata applicazione può causare un errore del servizio o dei client software. |
|||||

<!--
 [Reference: Experience – Post Migration][DNS]
-->

Per i servizi di terze parti per gli endpoint dei servizi di Office 365:

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Aggiornare i partner e i servizi di terze parti per gli endpoint dei servizi di Office 365. | -I servizi e i partner di terze parti che puntano a Office 365 Germany devono essere aggiornati in modo che puntino agli endpoint dei servizi di Office 365. Esempio: registrare di nuovo, in linea con i fornitori e i partner, la versione delle applicazioni della raccolta app, se disponibile. <br><br> -Puntare tutte le applicazioni personalizzate che sfruttano l'API del grafico da `graph.microsoft.de` a `graph.microsoft.com` . Anche altre API con endpoint modificati devono essere aggiornate, se vengono utilizzate. <br><br> -Modificare tutte le applicazioni Enterprise non di primo livello per reindirizzare gli endpoint in tutto il mondo.  | Tutti i clienti di Office | Azione obbligatoria. La mancata applicazione può causare un errore del servizio o dei client software. |
|||||

<!--
 [Reference: Experience – Post Migration][]
--> 

### <a name="exchange-online"></a>Exchange Online

Se si utilizza una configurazione di Exchange ibrida:

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Eseguire la procedura guidata di configurazione ibrida (HCW) per i servizi di Office 365. | La configurazione di HCW esistente ha lo scopo di supportare Microsoft Cloud Deutschland. Dopo aver completato la migrazione dei servizi di Exchange, si disaccoppia la configurazione locale da Microsoft Cloud Deutschland. | Clienti di Exchange Online che eseguono una distribuzione ibrida | Azione obbligatoria. La mancata applicazione può causare un errore del servizio o dei client software. Prima che la migrazione delle cassette postali di Exchange inizi (con almeno 5 giorni di preavviso), informare i client che devono interrompere ed eliminare eventuali spostamenti onboarding o offboarding delle proprie cassette postali.  In caso contrario, verranno visualizzati errori nelle richieste di spostamento. <br><br> -Dopo aver completato la migrazione delle cassette postali di Exchange, informare i client che possono riprendere l'onboarding e gli spostamenti di Offboarding. <br> L'esecuzione di **test-MigrationServerAvailabiilty**, un cmdlet di PowerShell, durante la migrazione di Exchange da Microsoft Cloud Deutschland a Office 365 Services potrebbe non funzionare. Tuttavia, funzionerà correttamente dopo il completamento della migrazione. <br><br> Se si verificano problemi con le credenziali o l'autorizzazione dopo la migrazione delle cassette postali, gli utenti possono immettere nuovamente le credenziali di amministratore locale nell'endpoint di migrazione eseguendo `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` o impostando lo stesso tramite il pannello di controllo di Exchange (ECP).  |

<!--
[Reference: Experience – Post Migration][Hybrid]  
[Reference: Experience – Post Migration][Exchange Online]
--> 

Per eDiscovery:

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
|  Tutti i percorsi di SharePoint Online, OneDrive for business e Exchange Online sono stati migrati insieme al centro sicurezza e conformità (SCC). | Tutte le attività di eDiscovery devono essere eseguite dal tenant di tutto il mondo. Le ricerche saranno ora 100% di esito positivo.  Gli errori o i problemi devono seguire i normali canali di supporto. | Tutti i clienti che utilizzano eDiscovery | Nessuna. |
| Rimuovere i criteri di conservazione a livello di organizzazione che sono stati creati durante la procedura di premigrazione | I clienti possono rimuovere i criteri di conservazione a livello dell'organizzazione creati durante il lavoro di premigrazione dei clienti. | Tutti i clienti che hanno applicato un criterio di conservazione come parte dei passaggi di premigrazione. | Nessuna. |
|||||

<!--
 [Reference: Experience – Post Migration][ [eDiscovery]             

[Reference: Experience – Post Migration][ [eDiscovery]
-->             

### <a name="sharepoint-online"></a>SharePoint Online

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Ripubblicare i flussi di lavoro di SharePoint 2013. | Nei lavori di premigrazione è stato ridotto il numero di flussi di lavoro di SharePoint 2013. Ora, con la migrazione completata, il cliente può ripubblicare i flussi di lavoro. | Tutti i clienti di Office | Si tratta di un'azione obbligatoria. La mancata operazione può comportare la confusione degli utenti e le chiamate del supporto tecnico. |
| Condividere gli elementi tramite Outlook | La condivisione di elementi tramite Outlook non funziona più dopo il tenant completa. | SharePoint Online e OneDrive for Business | -In SharePoint Online e OneDrive for business, è possibile condividere gli elementi tramite Outlook. Dopo aver premuto il pulsante Outlook, viene creato un collegamento condivisibile che viene inserito in un nuovo messaggio in Outlook Web App. <br><br> -Dopo il tenant completa, questo metodo di condivisione non funzionerà. Questo è un problema noto. Tuttavia, dal momento che questa funzionalità di Outlook si trova nel percorso obsoleto, la correzione del problema non viene pianificata fino a quando non viene srotolata la deprecazione. |

<!--
 [Reference: Experience – Post Migration][ [SPO]
-->

## <a name="next-step"></a>Passaggio successivo

[Comprendere le operazioni e gli impatti delle fasi di migrazione](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Altre informazioni

Guida introduttiva:

- [Migrazione da Microsoft Cloud Deutschland a Office 365 Services nelle nuove aree del datacenter tedesco](ms-cloud-germany-transition.md)
- [Assistenza per la migrazione di Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Come acconsentire esplicitamente a eseguire la migrazione](ms-cloud-germany-migration-opt-in.md)
- [Esperienza del cliente durante la migrazione](ms-cloud-germany-transition-experience.md)

Spostamento attraverso la transizione:

- [Operazioni e impatto delle fasi di migrazione](ms-cloud-germany-transition-phases.md)
- [Ulteriore prelavoro](ms-cloud-germany-transition-add-pre-work.md)
- Informazioni aggiuntive su [Servizi](ms-cloud-germany-transition-add-general.md), [dispositivi](ms-cloud-germany-transition-add-devices.md), [esperienze](ms-cloud-germany-transition-add-experience.md)e [ad FS](ms-cloud-germany-transition-add-adfs.md).

App Cloud:

- [Informazioni sul programma di migrazione di Dynamics 365](https://aka.ms/d365ceoptin)
- [Informazioni sul programma di migrazione di Power BI](https://aka.ms/pbioptin)
- [Guida introduttiva all'aggiornamento di Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
