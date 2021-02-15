---
title: Azioni e impatti delle fasi di migrazione per la migrazione da Microsoft Cloud Deutschland (generale)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 01/26/2021
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
description: 'Riepilogo: comprendere le azioni e gli effetti delle fasi di migrazione del passaggio da Microsoft Cloud Germania (Microsoft Cloud Deutschland) ai servizi di Office 365 nella nuova area data center tedesca.'
ms.openlocfilehash: 9dc2f4c0923f52bfc83a9177b595a6955a3afa8f
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242735"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>Azioni e impatti delle fasi di migrazione per la migrazione da Microsoft Cloud Deutschland (generale)

Le migrazioni dei tenant da Microsoft Cloud Deutschland all'area germania dei servizi di Office 365 di Microsoft vengono eseguite come set di fasi e le azioni configurate per ogni carico di lavoro. Questa figura mostra le nove fasi della migrazione ai nuovi datacenter tedeschi.

![Le nove fasi della migrazione ai nuovi datacenter tedeschi](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Le fasi e le relative azioni assicurano la migrazione di dati ed esperienze critici ai servizi di Office 365. Dopo l'aggiunta del tenant alla coda di migrazione, ogni carico di lavoro verrà completato come una serie di passaggi eseguiti nel servizio back-end. Alcuni carichi di lavoro possono richiedere azioni da parte dell'amministratore (o dell'utente) o la migrazione può influire sull'utilizzo per le fasi eseguite e illustrate in Come è organizzata [la migrazione?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

Nelle sezioni seguenti sono contenute azioni ed effetti per i carichi di lavoro durante le varie fasi della migrazione. Esaminare le tabelle e determinare quali azioni o effetti sono applicabili all'organizzazione. Assicurarsi di essere pronti a eseguire i passaggi nelle rispettive fasi in base alle esigenze. La mancata esecuzione dei passaggi necessari può causare un'interruzione del servizio e potrebbe ritardare il completamento della migrazione ai servizi di Office 365.

## <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (fase 4 di 9)

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| La transizione di SharePoint e OneDrive è in fase di transizione. | SharePoint e OneDrive vengono migrati da Microsoft Cloud Deutschland ai servizi di Office 365 in questa fase. Gli URL esistenti di Microsoft Cloud Deutschland vengono mantenuti (ad esempio, `contoso.sharepoint.de` ). I token emessi dai servizi Microsoft Cloud Deutschland o Office 365 sono validi durante la transizione. | Clienti di SharePoint | - Il contenuto sarà di sola lettura per due brevi periodi durante la migrazione. Durante questo periodo, è previsto un banner "non è possibile modificare il contenuto" in SharePoint. <br><br> - L'indice di ricerca non verrà conservato e la ricostruzione potrebbe richiedere fino a 10 giorni. <br><br> - Il contenuto di SharePoint/OneDrive sarà di sola lettura per due brevi periodi durante la migrazione. Gli utenti vedranno brevemente un banner "Non è possibile modificare il contenuto". <br><br> - L'indice di ricerca potrebbe non essere disponibile durante la ricostruzione dell'indice. Durante questo periodo, le query di ricerca potrebbero non restituire risultati completi. <br><br> - I siti esistenti vengono mantenuti. |
|||||

Considerazioni aggiuntive:

- Dopo aver completato la migrazione di SharePoint Online all'area tedesca, vengono ricreati gli indici dei dati. Le funzionalità che dipendono da indici di ricerca potrebbero essere interessate durante il completamento della reindicizzazione.

- Se nell'organizzazione vengono ancora utilizzati flussi di lavoro di SharePoint 2010, non funzioneranno più dopo il 31 dicembre 2021. I flussi di lavoro di SharePoint 2013 rimarranno supportati, anche se disattivati per impostazione predefinita per i nuovi tenant a partire dal 1° novembre 2020. Al termine della migrazione al servizio SharePoint Online, è consigliabile passare a Power Automate o ad altre soluzioni supportate.

- Al termine della migrazione di OneDrive nell'area tedesca, gli indici dei dati vengono ricostruiti. Le funzionalità che dipendono dagli indici di ricerca potrebbero essere interessate durante la reindicizzazione in corso.

- I clienti di Microsoft Cloud Deutschland la cui istanza di SharePoint Online non è ancora stata migrata devono rimanere nel modulo PowerShell di SharePoint Online/Microsoft.SharePointOnline.CSOM versione 16.0.20616.12000 o successiva. In caso contrario, le connessioni a SharePoint Online tramite PowerShell o il modello a oggetti sul lato client avranno esito negativo.

- I clienti di Microsoft Cloud Deutschland di cui viene eseguita la migrazione dell'istanza di SharePoint Online devono aggiornare il modulo PowerShell di SharePoint Online/Microsoft.SharePointOnline.CSOM alla versione 16.0.20717.12000 o successiva. In caso contrario, le connessioni a SharePoint Online tramite PowerShell o il modello a oggetti sul lato client avranno esito negativo.


## <a name="exchange-online-phase-5-of-9"></a>Exchange Online (fase 5 di 9)

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| La nuova area germania viene aggiunta alla configurazione dell'organizzazione esistente e le cassette postali vengono spostate nei servizi di Office 365. | La configurazione di Exchange Online aggiunge la nuova area tedesca go-local all'organizzazione di transizione. Questa area dei servizi di Office 365 è impostata come predefinita, che consente al servizio di bilanciamento del carico interno di ridistribuire le cassette postali nell'area predefinita appropriata nei servizi di Office 365. In questa transizione, gli utenti su entrambi i lati (germania o servizi di Office 365) sono nella stessa organizzazione e possono usare entrambi gli endpoint URL. | Exchange Online | - Eseguire la transizione di utenti e servizi dagli URL germania agli URL dei servizi di Office 365 ( `https://outlook.office365.com` ). <br><br> - Gli utenti continueranno ad accedere al servizio tramite URL Germania legacy durante la migrazione. Non è necessaria alcuna azione immediata. <br><br> - Gli utenti devono iniziare a usare il portale office.com per le funzionalità di Office Online (Calendario, Posta, Persone). L'esplorazione dei servizi non ancora migrati ai servizi di Office 365 non funzionerà finché non viene eseguita la migrazione. <br><br> - Outlook Web App non fornirà l'esperienza delle cartelle pubbliche durante la migrazione. |
|||||

Considerazioni aggiuntive:

- `myaccount.msft.com` funzionerà solo dopo il cutover di Office 365. Fino a quel momento, i collegamenti generano messaggi di errore che indicavano che si è verificato un problema.

- Agli utenti di Outlook Web App che accedono a una cassetta postale condivisa nell'altro ambiente (ad esempio, un utente nell'ambiente Germania accede a una cassetta postale condivisa nell'ambiente globale) verrà richiesto di eseguire l'autenticazione una seconda volta. L'utente deve prima autenticare e accedere alla propria cassetta postale in , quindi `outlook.office.de` aprire la cassetta postale condivisa in `outlook.office365.com` . Dovranno eseguire l'autenticazione una seconda volta quando accedono alle risorse condivise ospitate nell'altro servizio.

- Per i clienti esistenti di Microsoft Cloud Deutschland o per quelli in transizione, quando una cassetta postale condivisa viene aggiunta a Outlook tramite **File > Info > Aggiungi account,** la visualizzazione delle autorizzazioni del calendario potrebbe non riuscire (il client Outlook tenta di utilizzare l'API `https://outlook.office.de/api/v2.0/Me/Calendars` Rest). I clienti che desiderano aggiungere un account per visualizzare le autorizzazioni del calendario possono aggiungere la chiave del Registro di sistema come descritto in Modifiche dell'esperienza utente per la condivisione di un calendario [in Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) per garantire che questa azione abbia esito positivo. Questa chiave del Registro di sistema può essere distribuita a livello di organizzazione tramite Criteri di gruppo.

- Durante la fase di migrazione, l'utilizzo dei cmdlet di PowerShell **New-migrationEndpoint,** **Set-MigrationEndpoint** e **Test-MigrationsServerAvailability** può causare errori (errore nel proxy). Ciò si verifica quando la cassetta postale di arbitraggio è stata migrata in tutto il mondo, ma la cassetta postale dell'amministratore non ha o viceversa. Per risolvere il problema, durante la creazione della sessione di PowerShell tenant, utilizzare la cassetta postale di arbitraggio come suggerimento di routing in **ConnectionUri.** Ad esempio: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- Se si utilizza Exchange Online ibrido:

    - È necessario eseguire di nuovo la procedura guidata di configurazione ibrida (HCW) per aggiornare la configurazione locale con Microsoft Cloud Deutschland prima della transizione ed eseguire di nuovo HCW al momento della pulizia nei servizi di Office 365. Se si utilizzano domini personalizzati, potrebbero essere necessari ulteriori aggiornamenti DNS.

Per saperne di più sulle differenze per le organizzazioni nella migrazione e dopo la migrazione delle risorse di Exchange Online, consultare le informazioni in Customer Experience durante la migrazione ai servizi di [Office 365](ms-cloud-germany-transition-experience.md)nelle nuove aree data center tedesche.

## <a name="exchange-online-protection-phase-6-of-9"></a>Exchange Online Protection (fase 6 di 9)

Le funzionalità di Exchange Online Protection (EOP) back-end vengono copiate nella nuova area geografica germania. 

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Migrazione del routing di Exchange Online e dei dettagli cronologici dei messaggi. | Exchange Online consente il routing da host esterni a Office 365. I record MX esterni vengono indirizzati al servizio EOP. Viene eseguita la migrazione della configurazione del tenant e dei dettagli cronologici. | Clienti di Exchange Online | - Le voci DNS gestite da Microsoft vengono aggiornate da Office 365 Germany EOP ai servizi di Office 365. <br><br> - I clienti devono attendere 30 giorni dopo la doppia scrittura EOP per la migrazione EOP. In caso contrario, potrebbe verificarsi una perdita di dati. |
|||||



## <a name="skype-for-business-online-phase-7-of-9"></a>Skype for Business online (fase 7 di 9)

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Migrazione di Skype for Business a Teams. | I clienti skype for Business esistenti vengono migrati ai servizi di Office 365 in Europa e quindi vengono migrati a Microsoft Teams nell'area germania dei servizi di Office 365. | Clienti Skype for Business | - Gli utenti non potranno accedere a Skype for Business alla data di migrazione. Dieci giorni prima della migrazione, inseriamo nell'interfaccia di amministrazione per inserirvi informazioni su quando verrà completata la migrazione e di nuovo quando iniziamo la migrazione. <br><br> - Viene eseguita la migrazione della configurazione dei criteri. <br><br> - Gli utenti verranno migrati in Teams e non avranno più Skype for Business dopo la migrazione. <br><br> - Gli utenti devono avere installato il client desktop di Teams. L'installazione verrà eseguita durante i 10 giorni tramite criteri nell'infrastruttura di Skype for Business, ma in caso di errore, gli utenti dovranno comunque scaricare il client o connettersi con un browser supportato. <br><br> - I contatti e le riunioni verranno migrati in Teams. <br><br> - Gli utenti non saranno in grado di accedere a Skype for Business tra le transizioni dei servizi di tempo ai servizi di Office 365 e non fino al completamento delle voci DNS dei clienti. <br><br> - I contatti e le riunioni esistenti continueranno a funzionare come riunioni Skype for Business. |
|||||


## <a name="office-apps-phase-8-of-9"></a>App di Office (fase 8 di 9)

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Client, Office Online durante il cutover del client Office, Azure AD finalizza l'ambito tenant in modo che punti ai servizi di Office 365. | Questa modifica alla configurazione consente ai client di Office di eseguire l'aggiornamento e puntare agli endpoint dei servizi di Office 365. | Tutti i clienti di Office | - Informare gli utenti di chiudere tutte le app di _Office_ e quindi accedere nuovamente (o forzare il riavvio dei client e gli utenti ad accedere) per consentire ai client di Office di raccogliere la modifica. <br><br> - Notificare agli utenti  e al personale dell'help desk che gli utenti potrebbero visualizzare un banner di Office che chiede loro di riattivare le app di Office entro 72 ore dal cutover. <br><br> - Tutte le applicazioni di Office nei computer personali devono essere chiuse e gli utenti devono disconnettersi e quindi accedere di nuovo. Nella barra di attivazione gialla, accedere per riattivare i servizi di Office 365. <br><br> - I computer condivisi richiederanno azioni simili ai computer personali e non richiederanno una procedura speciale. <br><br> - Nei dispositivi mobili, gli utenti devono disconnettersi dall'app, chiuderle e quindi accedere di nuovo. |
|||||


## <a name="office-services"></a>Servizi di Office

L'ultimo servizio usato (MRU) in Office è un passaggio completo dal servizio Germania ai servizi di Office 365, non una migrazione. Solo i collegamenti MRU dal lato dei servizi di Office 365 saranno visibili dopo la migrazione dal Office.com portale. I collegamenti MRU dal servizio Germania non sono visibili come collegamenti MRU nei servizi di Office 365. In Office 365, i collegamenti MRU sono accessibili solo dopo il completamento della migrazione del tenant.

## <a name="subscription"></a>Abbonamento

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Non è possibile eseguire la migrazione dei clienti senza il consenso dell'utente. | Microsoft ottiene il diritto di eseguire la migrazione in uno dei due modi seguenti, che consente a Microsoft di orchestrare la transizione di dati e servizi all'istanza dei servizi di Office 365. <br> L'amministratore acconsente esplicitamente alla migrazione guidata da Microsoft. <br> I clienti rinnovano le sottoscrizioni nel tenant di Microsoft Cloud Deutschland dopo il 1° maggio 2020. Informeremo questi clienti del diritto di migrazione ogni mese, attendere 30 giorni per offrire ai clienti la possibilità di annullare e quindi acconsentire direttamente, tenere traccia in ICM. | Tutti i clienti di Office | - Il tenant è contrassegnato come autorizzato per la migrazione e l'interfaccia di amministrazione visualizza la conferma. <br><br> - Il riconoscimento viene pubblicato nel tenant del Centro messaggi cloud Germania. La configurazione del servizio continua dagli endpoint di Microsoft Cloud Deutschland. <br><br> - Monitorare il Centro messaggi per gli aggiornamenti sullo stato della fase di migrazione. |
| Le sottoscrizioni vengono trasferite e le licenze vengono riassegnate. | Dopo la transizione del tenant ai servizi di Office 365, gli abbonamenti ai servizi di Office 365 corrispondenti vengono acquistati per gli abbonamenti a Microsoft Cloud Deutschland trasferiti. Agli utenti con licenze di Microsoft Cloud Deutschland assegnate verranno assegnate le licenze dei servizi di Office 365. Le sottoscrizioni legacy di Microsoft Cloud Deutschland vengono rimosse dal tenant dei servizi di Office 365 al completamento. | Tutti i clienti di Office | - Le modifiche alle sottoscrizioni esistenti verranno bloccate (ad esempio, nessun nuovo acquisto di sottoscrizione o modifiche al numero di postazioni) durante questa fase. <br><br> - Le modifiche all'assegnazione delle licenze verranno bloccate. <br><br> - L'abbonamento a Microsoft Cloud Deutschland verrà migrato al corrispondente abbonamento ai servizi di Office 365. L'offerta di servizi di Office 365 di tale sottoscrizione è definita da Microsoft (nota anche come _mapping delle offerte)._ <br><br> - Il numero di funzionalità (piani di servizio) offerti dai servizi di Office 365 può essere maggiore rispetto all'offerta originale di Microsoft Cloud Deutschland. Le licenze utente nei servizi di Office 365 verranno assegnate in modo equivalente a funzionalità simili di Microsoft Cloud Deutschland (piani di servizio). Le licenze utente di tutti gli utenti verranno assegnate automaticamente alle nuove funzionalità. L'amministratore deve eseguire un'azione esplicita per disabilitare tali licenze, se necessario. <br><br> - Al termine della migrazione delle sottoscrizioni, sia i servizi di Office 365 che gli abbonamenti germania saranno visibili nel portale di amministrazione di Office 365, con lo stato di sottoscrizioni germania come _deprovisioning._ <br><br> - Agli utenti verranno riassegnate le licenze collegate ai nuovi abbonamenti ai servizi di Office 365. I processi dei clienti che hanno dipendenze dalle sottoscrizioni germania o dai GUID SKU verranno interrotti e dovranno essere rivisti con l'offerta di servizi di Office 365. <br><br> - Le nuove sottoscrizioni ai servizi di Office 365 verranno acquistate con il nuovo termine (mensile/trimestrale/annuale) e il cliente riceverà un rimborso ribilanciato per il saldo inutilizzato della sottoscrizione a Microsoft Cloud Deutschland. <br><br> - I tenant di Microsoft Cloud Deutschland partner non verranno migrati. I clienti CSP verranno migrati ai servizi di Office 365 nel nuovo tenant dei servizi di Office 365 dello stesso partner. Dopo la migrazione dei clienti, il partner può gestire questo cliente solo dal tenant dei servizi di Office 365. <br><br> - Sono disponibili funzionalità aggiuntive (ad esempio, Microsoft Planner e Microsoft Flow), a meno che non siano disabilitate dall'amministratore tenant. Per informazioni su come disabilitare i piani di servizio assegnati alle licenze degli utenti, vedere Disabilitare l'accesso ai servizi di [Microsoft 365](disable-access-to-services-while-assigning-user-licenses.md)durante l'assegnazione delle licenze utente.  |
|||||

## <a name="next-step"></a>Passaggio successivo

[Eseguire operazioni pre-lavorative aggiuntive](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>Ulteriori informazioni

Guida introduttiva:

- [Migrazione da Microsoft Cloud Deutschland ai servizi di Office 365 nelle nuove aree data center tedesche](ms-cloud-germany-transition.md)
- [Assistenza per la migrazione di Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Come acconsentire esplicitamente a eseguire la migrazione](ms-cloud-germany-migration-opt-in.md)
- [Esperienza del cliente durante la migrazione](ms-cloud-germany-transition-experience.md)

Spostamento attraverso la transizione:

- [Pre-lavoro aggiuntivo](ms-cloud-germany-transition-add-pre-work.md)
- Ulteriori informazioni per [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivi,](ms-cloud-germany-transition-add-devices.md) [esperienze](ms-cloud-germany-transition-add-experience.md)e [AD FS.](ms-cloud-germany-transition-add-adfs.md)

App cloud:

- [Informazioni sul programma di migrazione di Dynamics 365](https://aka.ms/d365ceoptin)
- [Informazioni sul programma di migrazione di Power BI](https://aka.ms/pbioptin)
- [Guida introduttiva all'aggiornamento di Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
