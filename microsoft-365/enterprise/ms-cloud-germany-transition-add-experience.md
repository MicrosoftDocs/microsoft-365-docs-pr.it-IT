---
title: Attività post-migrazione per la migrazione da Microsoft Cloud Deutschland
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
description: 'Riepilogo: attività post-migrazione dopo il passaggio da Microsoft Cloud Germania (Microsoft Cloud Deutschland) a servizi Office 365 nella nuova area data center tedesca.'
ms.openlocfilehash: ee8dedf7ffaf6bfc4246b1a8cc2522c15d763cd1
ms.sourcegitcommit: 1c53f114a810e7aaa2dc876b84d66348492ea36c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899365"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Attività post-migrazione per la migrazione da Microsoft Cloud Deutschland

Le sezioni seguenti forniscono attività post-migrazione per più servizi dopo il passaggio da Microsoft Cloud Germania (Microsoft Cloud Deutschland) a servizi Office 365 nella nuova area data center tedesca.

## <a name="azure-ad"></a>Azure AD
<!-- This AAD Endpoints comparison table could be added to the documentation, not finally decided.
### Azure AD Endpoints
**Applies to:** All customers

After the cut over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland and the endpoints cannot be used anymore. At this point, the customer needs to ensure that all applications are using the endpoints for the new German datacenter region.
The following table provides an overview about which endpoints will replace the previously used endpoints in Microsoft Cloud Germany (Microsoft Cloud Deutschland). 

|Endpoint in Microsoft Cloud Germany  |Endpoint in the new German datacenter region  |
|:---------|:---------|
|becws.microsoftonline.de<br>provisioningapi.microsoftonline.de |becws.microsoftonline.com<br>provisioningapi.microsoftonline.com |
|adminwebservice.microsoftonline.de |adminwebservice.microsoftonline.com |
|login.microsoftonline.de<br>logincert.microsoftonline.de<br>sts.microsoftonline.de |login.microsoftonline.com<br>login.windows.net<br>logincert.microsoftonline.com<br>accounts.accesscontrol.windows.net |
|enterpriseregistration.microsoftonline.de |enterpriseregistration.windows.net |
|graph.cloudapi.de |graph.windows.net |
|graph.microsoft.de |graph.microsoft.com |
|||
-->

### <a name="azure-ad-federated-authentication-with-ad-fs"></a>Autenticazione federata di Azure AD con ADFS
**Si applica a:** Tutti i clienti che usano l'autenticazione federata con ADFS

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Rimuovere attendibilità relying party da Microsoft Cloud Deutschland AD FS. | Al termine del cut-over ad Azure AD, l'organizzazione usa completamente i servizi Office 365 e non è più connessa a Microsoft Cloud Deutschland. A questo punto, il cliente deve rimuovere l'attendibilità del relying party per gli endpoint di Microsoft Cloud Deutschland. Questa operazione può essere eseguita solo quando nessuna delle applicazioni del cliente punta agli endpoint di Microsoft Cloud Deutschland quando Azure AD viene utilizzato come provider di identità (IdP). | Organizzazioni con autenticazione federata | Nessuna. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a>Approvazioni di gruppo
**Si applica a:** Utenti finali le cui richieste di approvazione di gruppo di Azure AD non sono state approvate negli ultimi 30 giorni prima della migrazione 

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Le richieste di partecipazione a un gruppo di Azure AD negli ultimi 30 giorni prima della migrazione dovranno essere nuovamente richieste se la richiesta originale non è stata approvata. | Se tali richieste non sono state approvate negli ultimi 30 giorni prima della migrazione, i clienti dell'utente finale dovranno usare il pannello di accesso per inviare di nuovo una richiesta di partecipazione a un gruppo di Azure AD. |  Come utente finale: <ol><li>Passare a [Pannello di accesso](https://account.activedirectory.windowsazure.com/r#/joinGroups).</li><li>Trovare un gruppo di Azure AD per il quale l'approvazione dell'appartenenza era in sospeso durante i 30 giorni precedenti la migrazione.</li><li>Richiedere di aggiungere di nuovo il gruppo di Azure AD.</li></ol> Le richieste di partecipazione a un gruppo attivo meno di 30 giorni prima della migrazione non possono essere approvate, a meno che non vengano richieste di nuovo dopo la migrazione. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
## <a name="custom-dns-updates"></a>Aggiornamenti DNS personalizzati
**Si applica a:**  Tutti i clienti che gestiscono le proprie zone DNS

| Step(s) | Descrizione | Impatto |
|:------|:-------|:-------|
| Aggiornare i servizi DNS locali per Office 365 endpoint dei servizi locali. | Le voci DNS gestite dal cliente che puntano a Microsoft Cloud Deutschland devono essere aggiornate in modo che puntino Office 365 endpoint dei servizi globali. | L'esito negativo di questa operazione può causare un errore del servizio o dei client software. |
||||

## <a name="third-party-services"></a>Servizi di terze parti
**Si applica a:** Clienti che usano servizi di terze parti per Office 365 endpoint dei servizi

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Aggiornare i partner e i servizi di terze parti per Office 365 endpoint. | <ul><li>I servizi e i partner di terze parti che puntano a Office 365 Germania devono essere aggiornati per puntare agli endpoint Office 365 services. Esempio: registrare di nuovo, in linea con i fornitori e i partner, la versione dell'app raccolta delle applicazioni, se disponibile. </li><li>Puntare tutte le applicazioni personalizzate che sfruttano Graph API da `graph.microsoft.de` a `graph.microsoft.com` . Anche altre API con endpoint modificati devono essere aggiornate, se sfruttate. </li><li>Modificare tutte le applicazioni aziendali non di prima parte in modo che reindirizzano agli endpoint globali. </li></ul>| Azione obbligatoria. L'esito negativo di questa operazione può causare un errore del servizio o dei client software. |
||||

## <a name="sharepoint-online"></a>SharePoint Online
**Si applica a:** Clienti che utilizzano SharePoint 2013

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Ripubblicare SharePoint 2013. | Nel lavoro di pre-migrazione, è stato ridotto il numero di flussi di lavoro SharePoint 2013. Al termine della migrazione, il cliente può ripubblicare i flussi di lavoro. | Si tratta di un'azione obbligatoria. La mancata operazione può causare confusione per l'utente e le chiamate all'help desk. |
| Condividere elementi tramite Outlook | La condivisione di elementi in SharePoint Online e OneDrive for Business tramite Outlook non funziona più dopo il cutover del tenant. |<ul><li>In SharePoint Online e OneDrive for Business, è possibile condividere elementi tramite Outlook. Dopo aver premuto il Outlook, viene creato un collegamento condivisibile e inserito in un nuovo messaggio nel Outlook Web App.</li><li>Dopo il cutover del tenant, questo metodo di condivisione non funzionerà. Riconosciamo che si tratta di un problema noto. Tuttavia, poiché questa Outlook è nel percorso della deprecazione, la correzione del problema non è pianificata fino all'implementazione della deprecazione. </li></ul>|
||||

## <a name="exchange-online"></a>Exchange Online
**Si applica a:** Clienti che usano una configurazione Exchange ibrida

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Eseguire di nuovo la procedura guidata di configurazione ibrida (HCW) Office 365 servizi. | La configurazione HCW esistente è destinata a supportare Microsoft Cloud Deutschland. Con la migrazione dei Exchange completa, disaccodiamo la configurazione locale da Microsoft Cloud Deutschland. |<ul><li>Azione obbligatoria. L'esito negativo di questa operazione può causare un errore del servizio o dei client software. Prima Exchange la migrazione delle cassette postali (con 5 o più giorni di preavviso), informare i client che devono interrompere ed eliminare eventuali spostamenti di onboarding o offboarding delle cassette postali.  In caso contrario, verranno visualizzati errori nelle richieste di spostamento. </li><li>Dopo Exchange migrazione delle cassette postali, informare i client che possono riprendere l'onboarding e gli spostamenti di offboarding. <br> L'esecuzione di **Test-MigrationServerAvailabiilty**, un cmdlet di PowerShell, durante la migrazione di Exchange da Microsoft Cloud Deutschland ai servizi Office 365 potrebbe non funzionare. Tuttavia, funzionerà correttamente al termine della migrazione. </li><li>Se i client si verificano problemi con le credenziali o l'autorizzazione dopo la migrazione delle cassette postali, gli utenti possono reimmigare le proprie credenziali di amministratore locale nell'endpoint di migrazione eseguendo o impostando lo stesso utilizzando il Pannello di controllo di `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` Exchange .ECP. </li></ul>|
