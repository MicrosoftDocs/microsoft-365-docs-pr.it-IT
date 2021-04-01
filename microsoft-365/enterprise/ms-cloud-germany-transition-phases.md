---
title: Azioni e impatti delle fasi di migrazione per la migrazione da Microsoft Cloud Deutschland (generale)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/05/2021
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
description: 'Riepilogo: comprendere le azioni e gli impatti delle fasi di migrazione del passaggio da Microsoft Cloud Germania (Microsoft Cloud Deutschland) ai servizi di Office 365 nella nuova area dati tedesca.'
ms.openlocfilehash: ca24fff5e8b18128c55288352e65aa3cecfe3d81
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476614"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>Azioni e impatti delle fasi di migrazione per la migrazione da Microsoft Cloud Deutschland (generale)

Le migrazioni dei tenant da Microsoft Cloud Deutschland (MCD) all'area "Germania" dei servizi globali di Office 365 di Microsoft vengono eseguite come set di fasi e le azioni configurate per ogni carico di lavoro. Questa figura mostra le dieci fasi della migrazione ai nuovi datacenter tedeschi.

![Le dieci fasi della migrazione ai nuovi datacenter tedeschi](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Il processo di migrazione verrà completato per molte settimane a seconda delle dimensioni e della complessità complessive dell'organizzazione. Mentre la migrazione è in corso, gli utenti e gli amministratori possono continuare a utilizzare i servizi con le modifiche più dettagliate in questa documentazione. La grafica e la tabella definiscono le fasi e i passaggi durante la migrazione.

|Passaggio|Durata|Parte responsabile|Descrizione|
|:--------|:--------|:--------|:--------|
|Opt-In|Ore|Cliente|Scegliere l'organizzazione per la migrazione.|
|Pre-work|Giorni|Cliente|Completare il lavoro necessario per preparare utenti, workstation e rete per la migrazione.|
|Azure Active Directory (Azure AD)|1-2 giorni|Microsoft|Eseguire la migrazione dell'organizzazione di Azure AD a livello mondiale.|
|Azure|Settimane|Cliente|Creare nuove sottoscrizioni di Azure in tutto il mondo e eseguire la transizione dei servizi di Azure.|
|Transizione & licenze di sottoscrizione|1-2 giorni|Microsoft|Acquistare abbonamenti in tutto il mondo, annullare gli abbonamenti a Microsoft Cloud Deutschland e effettuare la transizione delle licenze utente.|
|SharePoint e OneDrive|15+ giorni|Microsoft|Eseguire la migrazione del contenuto di SharePoint e OneDrive for Business, conservando sharepoint.de URL.|
|Exchange Online|15+ giorni|Microsoft|Eseguire la migrazione del contenuto di Exchange Online e la transizione agli URL di tutto il mondo.|
|Sicurezza e conformità|1-2 giorni|Microsoft|Sicurezza della transizione & criteri di conformità e contenuto.|
|Skype for Business|1-2 giorni|Microsoft|Transizione da Skype for Business a Microsoft Teams.|
|Power BI & Dynamics 365|15+ giorni|Microsoft|Eseguire la migrazione del contenuto di Power BI e Dynamics 365.|
|Finalizzare Azure AD|1-2 giorni|Microsoft|Completare il cutover del tenant in tutto il mondo.|
|Clean-Up|1-2 giorni|Cliente|Pulire le connessioni legacy a Microsoft Cloud Deutschland, ad esempio active directory Federation Services (AD FS) Relying Party Trust, Azure AD Connect e riavvii client di Office.|
|Endpoint disabilitati|30 giorni|Microsoft|30 giorni dopo la finalizzazione di Azure AD, il servizio Microsoft Cloud Deutschland Azure AD interromperà l'accesso agli endpoint per l'organizzazione in transizione. Le richieste degli endpoint, ad esempio l'autenticazione, avranno esito negativo da questo punto in avanti nel servizio Microsoft Cloud Deutschland. |


Le fasi e le relative azioni garantiscono la migrazione di dati ed esperienze critiche ai servizi globali di Office 365. Dopo l'aggiunta del tenant alla coda di migrazione, ogni carico di lavoro verrà completato come una serie di passaggi eseguiti nel servizio back-end. Alcuni carichi di lavoro possono richiedere azioni da parte dell'amministratore (o dell'utente) o la migrazione può influire sull'utilizzo per le fasi eseguite e illustrate in Come è organizzata [la migrazione?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

Le sezioni seguenti contengono azioni ed effetti per i carichi di lavoro durante le varie fasi della migrazione. Esaminare le tabelle e determinare quali azioni o effetti sono applicabili all'organizzazione. Assicurarsi di essere pronti a eseguire i passaggi nelle rispettive fasi in base alle esigenze. La mancata esecuzione dei passaggi necessari può causare un'interruzione del servizio e potrebbe ritardare il completamento della migrazione ai servizi di Office 365.

## <a name="opt-in"></a>Opt-In

**Si applica a:** Tutti i clienti con un tenant di Office 365 ospitato in Microsoft Cloud Deutschland (MCD)

| Step(s) | Descrizione | Impatto |
|:-------|:-----|:-------|
| Non è possibile eseguire la migrazione dei tenant di Office 365 ospitati nel mcd senza il consenso. | Microsoft ottiene il diritto di eseguire la migrazione in uno dei due modi seguenti, che consente a Microsoft di orchestrare la transizione di dati e servizi all'istanza dei servizi globali di Office 365. <ol><li>L'amministratore tenant di Office 365 acconsente esplicitamente alla migrazione guidata da Microsoft. </li><li> I clienti rinnovano tutte le sottoscrizioni nel tenant mcD di Office 365 dopo il 1° maggio 2020. Informeremo questi clienti del diritto di migrazione ogni mese, attendere 30 giorni per offrire ai clienti la possibilità di annullare e quindi acconsentire direttamente.</li></ol> | <ul><li>Il tenant è contrassegnato come autorizzato per la migrazione e l'interfaccia di amministrazione visualizza la conferma. </li><li>Il riconoscimento viene inviato al Centro messaggi tenant di Office 365. La configurazione del servizio continua dagli endpoint di Microsoft Cloud Deutschland. </li><li>L'amministratore tenant deve monitorare il Centro messaggi di Office 365 per gli aggiornamenti sullo stato della fase di migrazione. </li></ul>|

## <a name="before-the-migration-starts"></a>Prima dell'inizio della migrazione

Assicurarsi di avere familiarità con i passaggi di preparazione [della migrazione che si applicano a tutti i clienti](ms-cloud-germany-transition-add-pre-work.md).

Nel caso in cui sia stato impostato un CNAME DNS denominato _msoid_ in uno o più spazi dei nomi DNS di cui si è proprietari, è necessario rimuovere il CNAME fino alla fine della fase 8 al più tardi. È possibile rimuovere il _msoid_ CNAME in qualsiasi momento prima della fine della fase 8. Vedere la [documentazione preliminare per DNS](ms-cloud-germany-transition-add-pre-work.md#dns).

Nel caso in cui si utilizzi l'accesso Single #A0 per Office 365 e Azure nell'istanza di Microsoft Cloud Deutschland, è necessario preparare e pianificare la migrazione della sottoscrizione di Azure di conseguenza. Assicurarsi di aver compreso i [prelavori per Microsoft Azure](ms-cloud-germany-transition-add-pre-work.md#microsoft-azure).

## <a name="before-phase-2-starts"></a>Prima dell'inizio della fase 2

Se si utilizza ADFS, assicurarsi di eseguire il backup della configurazione [di ADFS prima](ms-cloud-germany-transition-azure-ad.md) e dopo l'aggiunta dell'attendibilità del componente per il servizio globale di Office 365.

## <a name="subscription-transfer-phase-3"></a>Trasferimento della sottoscrizione (Fase 3)

**Si applica a:** Tutti i clienti con un tenant di Office 365 ospitato in Microsoft Cloud Deutschland (MCD)

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Le sottoscrizioni vengono trasferite e le licenze vengono riassegnate. | Le sottoscrizioni dei servizi globali di Office 365 corrispondenti vengono acquistate nell'istanza globale di Office 365 per le sottoscrizioni Microsoft Cloud Deutschland trasferite. Agli utenti con licenze di Microsoft Cloud Deutschland assegnate verranno assegnate licenze nell'istanza globale di Office 365. Le sottoscrizioni Legacy di Microsoft Cloud Deutschland vengono rimosse dal tenant dei servizi di Office 365 al completamento.| <ul><li>Le modifiche apportate alle sottoscrizioni esistenti verranno bloccate (ad esempio, non verranno apportate modifiche al numero di nuovi abbonamenti o al numero di postazioni) durante questa fase.</li><li>Le modifiche all'assegnazione delle licenze verranno bloccate.</li><li>L'abbonamento a Microsoft Cloud Deutschland verrà migrato all'abbonamento ai servizi globali di Office 365 corrispondente. L'offerta di servizi globali di Office 365 di tale sottoscrizione è definita da Microsoft (nota anche come _mapping delle offerte)._</li><li>Il numero di funzionalità (piani di servizio) offerti dai servizi di Office 365 può essere superiore a quello dell'offerta originale di Microsoft Cloud Deutschland. Le licenze utente nei servizi di Office 365 verranno assegnate in modo equivalente a funzionalità di Microsoft Cloud Deutschland simili (piani di servizio). Le licenze utente di tutti gli utenti verranno assegnate automaticamente alle nuove funzionalità. L'amministratore deve eseguire un'azione esplicita per disabilitare tali licenze, se necessario. </li><li>Al termine della migrazione delle sottoscrizioni, sia i servizi di Office 365 che gli abbonamenti a Microsoft Cloud Deutschland saranno visibili nel portale di amministrazione di Office 365, con lo stato di sottoscrizioni Microsoft Cloud Deutschland come _deprovisioned_. </li><li>Agli utenti verranno riassegnate le licenze collegate alle nuove sottoscrizioni ai servizi di Office 365. Tutti i processi dei clienti che hanno dipendenze dalle sottoscrizioni Microsoft Cloud Deutschland o dai GUID SKU verranno interrotti e dovranno essere rivisti con l'offerta di servizi di Office 365. </li><li>Le nuove sottoscrizioni nei servizi di Office 365 verranno acquistate con il nuovo termine (mensile/trimestrale/annuale) e il cliente riceverà un rimborso rateizzato per il saldo inutilizzato dell'abbonamento a Microsoft Cloud Deutschland. </li><li>I tenant di Microsoft Cloud Deutschland partner non verranno migrati. I clienti CSP verranno migrati ai servizi di Office 365 nel nuovo tenant dei servizi di Office 365 dello stesso partner. Dopo la migrazione del cliente, il partner può gestire questo cliente solo dal tenant dei servizi di Office 365. </li><li>Sono disponibili funzionalità aggiuntive, ad esempio Microsoft Planner e Microsoft Flow, a meno che non siano disabilitate dall'amministratore tenant. Per informazioni su come disabilitare i piani di servizio assegnati alle licenze degli utenti, vedere [Disable access to Microsoft 365 services while assigning user licenses](disable-access-to-services-while-assigning-user-licenses.md).</li></ul> |
||||

## <a name="sharepoint-online-phase-4"></a>SharePoint Online (fase 4)

**Si applica a**: Tutti i clienti che usano SharePoint Online

Nel caso in cui si utilizzino ancora flussi di lavoro di SharePoint 2013, limitare l'utilizzo dei flussi di lavoro di SharePoint 2013 durante la migrazione di SharePoint Online.

| Step(s) | Descrizione | Impatto |
|:-------|:-----|:-------|
| SharePoint e OneDrive sono in transizione | SharePoint Online e OneDrive for Business vengono migrati da Microsoft Cloud Deutschland ai servizi globali di Office 365 in questa fase.<br><ul><li>Gli URL esistenti di Microsoft Cloud Deutschland vengono mantenuti (ad esempio, `contoso.sharepoint.de` ).</li><li>I siti esistenti vengono mantenuti.</li><li>I token di autenticazione sul lato client emessi dal servizio token di sicurezza (STS) nell'istanza dei servizi Microsoft Cloud Deutschland o Office 365 Global sono validi durante la transizione.</li></ul>|<ul><li>Il contenuto sarà di sola lettura per due brevi periodi durante la migrazione. Durante questo periodo di tempo, è previsto un banner "non è possibile modificare il contenuto" in SharePoint.</li><li>L'indice di ricerca non verrà conservato e la ricostruzione potrebbe richiedere fino a 10 giorni.</li><li>Il contenuto di SharePoint Online e OneDrive for Business sarà di sola lettura per due brevi periodi durante la migrazione. Durante questo periodo, gli utenti vedranno un banner "Non è possibile modificare il contenuto".</li><li>Al termine della migrazione di SharePoint Online, i risultati della ricerca per il contenuto di SharePoint Online e OneDrive for Business potrebbero non essere disponibili durante la ricostruzione dell'indice. Durante questo periodo, le query di ricerca potrebbero non restituire risultati completi. Le funzionalità che dipendono da indici di ricerca, ad esempio Notizie di SharePoint Online, potrebbero essere interessate durante il completamento della reindicizzazione.</li><li>I flussi di lavoro di SharePoint 2013 verranno interrotti durante la migrazione e devono essere ripubblicati dopo la migrazione.</li></ul>|
||||

Considerazioni aggiuntive:

- Se l'organizzazione utilizza ancora flussi di lavoro di SharePoint 2010, non funzioneranno più dopo il 31 dicembre 2021. I flussi di lavoro di SharePoint 2013 rimarranno supportati, anche se disattivati per impostazione predefinita per i nuovi tenant a partire dal 1 novembre 2020. Al termine della migrazione al servizio SharePoint Online, è consigliabile passare a Power Automate o ad altre soluzioni supportate.

- I clienti di Microsoft Cloud Deutschland la cui istanza di SharePoint Online non è ancora stata migrata devono rimanere nel modulo PowerShell di SharePoint Online/Microsoft.SharePointOnline.CSOM versione 16.0.20616.12000 o successiva. In caso contrario, le connessioni a SharePoint Online tramite PowerShell o il modello a oggetti sul lato client avranno esito negativo.

- I clienti di Microsoft Cloud Deutschland di cui viene eseguita la migrazione dell'istanza di SharePoint Online devono aggiornare il modulo PowerShell di SharePoint Online/Microsoft.SharePointOnline.CSOM alla versione 16.0.20717.12000 o successiva. In caso contrario, le connessioni a SharePoint Online tramite PowerShell o il modello a oggetti sul lato client avranno esito negativo.

> [!NOTE]
> Nel caso in cui si utilizzi eDiscovery, assicurarsi di essere a conoscenza [dell'esperienza di migrazione di eDiscovery.](ms-cloud-germany-transition-add-experience.md#ediscovery-phase-4-to-the-end-of-phase-9)

## <a name="exchange-online-phase-5"></a>Exchange Online (fase 5)

**Si applica a:** Tutti i clienti che utilizzano Exchange Online

Se si utilizza exchange Online ibrido: gli amministratori della distribuzione ibrida di Exchange Online devono eseguire la procedura guidata di configurazione ibrida  **(HCW)** più volte come parte di questa transizione. Applicare le [prelavorazioni di Exchange](ms-cloud-germany-transition-add-pre-work.md#exchange-online-hybrid-configuration) **prima dell'inizio della fase 5 della migrazione.** I clienti ibridi di Exchange Online devono eseguire la versione più recente della procedura guidata di configurazione ibrida di Exchange (HCW) in modalità "Office 365 Germany" per preparare la configurazione locale per la migrazione ai servizi globali di Office 365.

Al termine della fase di migrazione **9** (quando viene pubblicato l'avviso del Centro messaggi), è necessario eseguire di nuovo HCW usando le impostazioni di Office 365 Worldwide per puntare i sistemi locali ai servizi globali di Office 365.

Se si desidera modificare le foto degli utenti durante la fase 5, vedere [Exchange Online Set-UserPhoto durante la fase 5](ms-cloud-germany-transition-add-experience.md#exchange-online-set-userphoto-during-phase-5)

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
|Arrestare o eliminare gli spostamenti delle cassette postali di onboarding o offboarding, in modo da non spostare le cassette postali tra Exchange locale ed Exchange Online.  | In questo modo le richieste di spostamento delle cassette postali non hanno esito negativo con un errore. | L'esito negativo di questa operazione può causare un errore del servizio o dei client di Office. |
| Le cassette postali di Exchange Online vengono spostate da Microsoft Cloud Deutschland ai servizi globali di Office 365.| La configurazione di Exchange Online aggiunge la nuova area tedesca locale all'organizzazione di transizione. L'area dei servizi globali di Office 365 è impostata come predefinita, che consente al servizio di bilanciamento del carico interno di ridistribuire le cassette postali nell'area predefinita appropriata nei servizi di Office 365. In questa transizione, gli utenti su entrambi i lati (mcd o servizi globali) si stanno nella stessa organizzazione e possono usare entrambi gli endpoint URL. |<ul><li>Eseguire la transizione di utenti e servizi dagli URL MCD legacy (outlook.office.de) ai nuovi URL dei servizi di Office 365 ( `https://outlook.office365.com` ).</li><li>Gli utenti possono continuare ad accedere al servizio tramite URL MCD legacy durante la migrazione, tuttavia devono smettere di usare gli URL legacy al termine della migrazione.</li><li>Gli utenti devono passare all'utilizzo del portale di Office globale per le funzionalità di Office Online (Calendario, Posta, Persone). L'esplorazione dei servizi non ancora migrati nei servizi di Office 365 non funzionerà finché non viene eseguita la migrazione. </li><li>Outlook Web App non fornirà l'esperienza delle cartelle pubbliche durante la migrazione. </li></ul>|
| Aggiornare le impostazioni DNS personalizzate per l'individuazione automatica| Le impostazioni DNS gestite dal cliente per l'individuazione automatica che attualmente puntano a Microsoft Cloud Deutschland devono essere aggiornate per fare riferimento all'endpoint globale di Office 365 al completamento della fase di Exchange Online (fase 5). <br> Le voci DNS esistenti con CNAME che puntano autodiscover-outlook.office.de devono essere aggiornate in modo che puntino a autodiscover.outlook.com. |  Richieste di disponibilità e chiamate di individuazione dei servizi tramite il punto di individuazione automatica direttamente ai servizi di Office 365. I clienti che non eseguono questi aggiornamenti DNS potrebbero verificarsi problemi del servizio di individuazione automatica quando la migrazione viene finalizzata. |
| Gli utenti devono aggiornare la configurazione del client POP3, IMAP4 e SMTP. | Gli utenti che dispongono di connessioni di dispositivi agli endpoint Microsoft Cloud Deutschland per i protocolli client POP3, IMAP4, SMTP devono aggiornare manualmente i dispositivi client per passare agli endpoint di [Office 365](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide) in tutto il mondo contemporaneamente alla migrazione delle cassette postali all'area di Office 365 Germany. <br> smtp.office365.com : SMTP (TCP:587), outlook.office365.com : IMAP4 (TCP:993), POP3 (TCP:995)| Gli utenti di questi protocolli devono passare a utilizzare Outlook mobile o Outlook sul Web mentre la cassetta postale viene trascritta e aggiornare le impostazioni IMAP4, POP3, SMTP nei dispositivi client ai nuovi endpoint al completamento. Se non si aggiornano gli endpoint client, si verificano errori di connessione client su Microsoft Cloud Deutschland durante la migrazione delle cassette postali degli utenti. |
||||

Considerazioni aggiuntive:
<!--
    The statement below is not clear. What does myaccount.microsoft.com mean?
-->

- `myaccount.microsoft.com` funzionerà solo dopo il cutover del tenant nella fase 9. I collegamenti genereranno messaggi di errore "si è verificato un problema" fino a quel momento.

- Agli utenti di Outlook Web App che accedono a una cassetta postale condivisa nell'altro ambiente (ad esempio, un utente nell'ambiente MCD accede a una cassetta postale condivisa nell'ambiente globale) verrà richiesto di eseguire l'autenticazione una seconda volta. L'utente deve prima autenticare e accedere alla propria cassetta postale in `outlook.office.de` , quindi aprire la cassetta postale condivisa in `outlook.office365.com` . Dovranno eseguire l'autenticazione una seconda volta quando accedono alle risorse condivise ospitate nell'altro servizio.

- Per i clienti Microsoft Cloud Deutschland esistenti o quelli in transizione, quando una cassetta postale condivisa viene aggiunta a Outlook utilizzando **File > Info > Aggiungi account**, la visualizzazione delle autorizzazioni del calendario potrebbe non riuscire (il client Outlook tenta di utilizzare l'API Rest `https://outlook.office.de/api/v2.0/Me/Calendars` ). I clienti che desiderano aggiungere un account per visualizzare le autorizzazioni del calendario possono aggiungere la chiave del Registro di sistema come descritto in [User experience changes for sharing a calendar in Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) per garantire che questa azione abbia esito positivo. Questa chiave del Registro di sistema può essere distribuita a livello di organizzazione tramite Criteri di gruppo.

- Durante la fase di migrazione, l'utilizzo dei cmdlet di PowerShell **New-migrationEndpoint,** **Set-MigrationEndpoint** e **Test-MigrationsServerAvailability** può causare errori (errore nel proxy). Ciò accade quando la cassetta postale di arbitraggio è stata migrata in tutto il mondo, ma la cassetta postale di amministrazione non è stata o viceversa. Per risolvere il problema, durante la creazione della sessione di PowerShell tenant, utilizzare la cassetta postale di arbitraggio come suggerimento di routing in **ConnectionUri**. Ad esempio:

```powershell
New-PSSession 
    -ConfigurationName Microsoft.Exchange 
    -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de"
    -Credential $UserCredential
    -Authentication Basic
    -AllowRedirection
```

Per ulteriori informazioni sulle differenze per le organizzazioni nella migrazione e dopo la migrazione delle risorse di Exchange Online, esaminare le informazioni in [Customer experience during the migration to Office 365 services in the new German datacenter regions](ms-cloud-germany-transition-experience.md).

## <a name="exchange-online-protection--security-and-compliance-phase-6"></a>Exchange Online Protection / Sicurezza e conformità (fase 6)

**Si applica a:** Tutti i clienti che utilizzano Exchange Online<br>

Le funzionalità back-end di Exchange Online Protection (EOP) vengono copiate nella nuova area geografica "Germania".

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Migrazione del routing di Exchange Online e dei dettagli cronologici dei messaggi. | Exchange Online consente il routing da host esterni a Office 365. I record MX esterni vengono instradati al servizio EOP. Viene eseguita la migrazione della configurazione del tenant e dei dettagli cronologici. |<ul><li>Le voci DNS gestite da Microsoft vengono aggiornate da Office 365 Germany EOP ai servizi di Office 365.</li><li>I clienti devono attendere 30 giorni dopo la doppia scrittura EOP per la migrazione EOP. In caso contrario, potrebbe verificarsi una perdita di dati.</li></ul>|
||||

## <a name="skype-for-business-online-phase-7"></a>Skype for Business online (fase 7)

**Si applica a:** Tutti i clienti che usano Skype for Business online

Assicurarsi di avere familiarità con la procedura di migrazione di [Skype for Business Online.](ms-cloud-germany-transition-add-pre-work.md#skype-for-business-online)

<!--
    Question from ckinder
    the PowerShell command seems to be incomplete
-->

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Migrazione di Skype for Business a Teams. | I clienti Skype for Business esistenti vengono migrati ai servizi globali di Office 365 in Europa e quindi vengono migrati a Microsoft Teams nell'area "Germania" dei servizi di Office 365. |<ul><li>Gli utenti non potranno accedere a Skype for Business alla data di migrazione. Dieci giorni prima della migrazione, inseriamo nell'interfaccia di amministrazione per sapere quando verrà completata la migrazione e di nuovo quando inizieremo la migrazione.</li><li> Viene eseguita la migrazione della configurazione dei criteri. </li><li>Gli utenti verranno migrati in Teams e non avranno più Skype for Business dopo la migrazione. </li><li>Gli utenti devono avere installato il client desktop di Teams. L'installazione verrà eseguita durante i 10 giorni tramite criteri nell'infrastruttura di Skype for Business, ma in caso di errore, gli utenti dovranno comunque scaricare il client o connettersi con un browser supportato. </li><li>I contatti e le riunioni verranno migrati in Teams.</li><li>Gli utenti non potranno accedere a Skype for Business tra le transizioni dei servizi di tempo ai servizi di Office 365 e non fino al completamento delle voci DNS dei clienti. </li><li>I contatti e le riunioni esistenti continueranno a funzionare come riunioni Skype for Business. </li></ul>|
||||

Se devi connetterti a Skype for Business online con PowerShell dopo il completamento della fase di migrazione 9, usa il codice seguente per connetterti:

```powershell
Import-Module MicrosoftTeams
$userCredential = Get-Credential
Connect-MicrosoftTeams -Credential $userCredential -OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"
```

## <a name="dynamics-365-phase-8"></a>Dynamics 365 (Fase 8)

**Si applica a:** Tutti i clienti che usano Microsoft Dynamics 365

Assicurarsi di avere familiarità con le attività di pre-elaborazione per la procedura di installazione di [Microsoft Dynamics 365.](ms-cloud-germany-transition-add-pre-work.md#dynamics365)

I clienti con Dynamics 365 richiedono un impegno aggiuntivo per eseguire la migrazione indipendente delle organizzazioni Dynamics dell'organizzazione.

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Risorse di Microsoft Dynamics | I clienti con Microsoft Dynamics saranno impegnati da Microsoft Engineering o Microsoft FastTrack per la transizione di Microsoft Dynamics 365 all'istanza dei servizi globali di Office 365.* |<ul><li>Dopo la migrazione, l'amministratore convalida l'organizzazione. <</li><li>L'amministratore modifica i flussi di lavoro, se necessario. </li><li>L'amministratore cancella la modalità AdminOnly in base alle esigenze.</li><li>L'amministratore modifica il tipo di organizzazione _da Sandbox_, in base alle esigenze</li><li>Informare gli utenti finali del nuovo URL per accedere all'istanza (org).</li><li>Aggiornare tutte le connessioni in ingresso al nuovo URL dell'endpoint. </li><li>Il servizio Dynamics non sarà disponibile per gli utenti durante la transizione. </li><li>Gli utenti devono convalidare l'integrità e le funzionalità dell'organizzazione dopo la migrazione di ogni organizzazione.</li></ul>|
||||

\* (i) I clienti con Microsoft Dynamics 365 devono intervenire in questo scenario di migrazione come definito dal processo di migrazione fornito. (ii) Se il cliente non riesce a eseguire un'azione, Microsoft non sarà in grado di completare la migrazione. (iii) Quando Microsoft non è in grado di completare la migrazione a causa dell'inazione del cliente, la sottoscrizione del cliente scadrà il 29 ottobre 2021.

## <a name="power-bi-phase-8"></a>Power BI (fase 8)

**Si applica a:** Tutti i clienti che usano Microsoft Power BI (PBI)

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Migrazione delle risorse di Power BI | I clienti con Microsoft Power BI (PBI) verranno coinvolti da Microsoft Engineering o Microsoft FastTrack dopo aver attivato manualmente uno strumento di migrazione PBI esistente per eseguire la transizione di Power BI all'istanza dei servizi globali di Office 365.\*\* |<ul><li>Gli elementi di Power BI seguenti _non_ verranno transizionati e doranno essere ri-creati: <</li><li>Set di dati in tempo reale,ad esempio set di dati di streaming o push. </li><li>Configurazione e origine dati del gateway dati di Power BI locale. </li><li>I report creati in base ai set di dati in tempo reale non saranno disponibili dopo la migrazione e devono essere ricreati. </li><li>I servizi Power BI non saranno disponibili per gli utenti durante la transizione. L'inabilità del servizio non deve essere superiore a 24 ore.</li><li>Gli utenti doranno riconfigurare le origini dati e i relativi gateway dati locali con il servizio Power BI dopo la migrazione.  Fino a quando non lo fanno, gli utenti non saranno in grado di utilizzare queste origini dati per eseguire l'aggiornamento pianificato e/o le query dirette su tali origini dati. </li><li>Non è possibile eseguire la migrazione delle capacità e delle aree di lavoro premium. I clienti devono eliminare tutte le capacità prima della migrazione e crearle di nuovo dopo la migrazione. Spostare di nuovo le aree di lavoro nelle capacità desiderate.</li></ul>  |
||||

\*\* (i) I clienti con Microsoft Power BI devono intervenire in questo scenario di migrazione come definito dal processo di migrazione fornito. (ii) Se il cliente non riesce a eseguire un'azione, Microsoft non sarà in grado di completare la migrazione. (iii) Quando Microsoft non è in grado di completare la migrazione a causa dell'inazione del cliente, la sottoscrizione del cliente scadrà il 29 ottobre 2021.

## <a name="azure-ad-finalization-phase-9-10"></a>Finalizzazione di Azure AD (Fase 9, 10)

**Si applica a:** Tutti i clienti

Quando il tenant di Office 365 completa il passaggio finale della migrazione [Azure AD Finalization (Fase 9)] tutti i servizi vengono transitati a livello mondiale. Nessuna applicazione o utente deve accedere alle risorse per il tenant in uno qualsiasi degli endpoint di Microsoft Cloud Deutschland. Automaticamente, 30 giorni dopo il completamento della finalizzazione, il servizio Microsoft Cloud Deutschland Azure AD interromperà l'accesso degli endpoint per il tenant di transizione. Le richieste degli endpoint, ad esempio l'autenticazione, avranno esito negativo da questo punto in avanti nel servizio Microsoft Cloud Deutschland. 

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Aggiornare gli endpoint utente | Verificare che tutti gli utenti accertano il servizio utilizzando gli endpoint Microsoft in tutto il mondo adeguati |30 giorni dopo la finalizzazione della migrazione, gli endpoint di Microsoft Cloud Deutschland smetteranno di rispettare le richieste; il traffico del client o dell'applicazione avrà esito negativo.  |
| Aggiornare gli endpoint dell'applicazione Azure AD | È necessario aggiornare gli endpoint di Autenticazione, Azure Active Directory (Azure AD) e MS Graph per le applicazioni a quelli del servizio Microsoft Worldwide. | 30 giorni dopo la finalizzazione della migrazione, gli endpoint di Microsoft Cloud Deutschland smetteranno di rispettare le richieste; il traffico del client o dell'applicazione avrà esito negativo. |
||||

## <a name="office-apps"></a>Office Apps

**Si applica a:** Tutti i clienti che utilizzano applicazioni desktop di Office (Word, Excel, PowerPoint, Outlook, ...)

I tenant di Office 365 che effettuano la transizione all'area "Germania" richiedono a tutti gli utenti di chiudere, disconnettersi da Office 365 e accedere di nuovo per tutte le applicazioni desktop di Office (Word, Excel, PowerPoint, Outlook e così via) e il client OneDrive for Business dopo che la migrazione del tenant ha raggiunto la fase 9. La disconnessione e l'accesso consentono ai servizi di Office di ottenere nuovi token di autenticazione dal servizio Azure AD globale.

Assicurati di aver completato la [procedura preliminare per i dispositivi](ms-cloud-germany-transition-add-pre-work.md#mobile-device-management) mobili.

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Client, Office Online durante il cutover del client di Office, Azure AD finalizza l'ambito tenant in modo che punti ai servizi di Office 365. | Questa modifica della configurazione consente ai client di Office di aggiornare e puntare agli endpoint dei servizi di Office 365. | <ul><li>Informare gli utenti di chiudere _tutte_ le app di Office e quindi accedere di nuovo (o forzare il riavvio dei client e gli utenti ad accedere) per consentire ai client di Office di ritirare la modifica. </li><li>Informare gli utenti e  il personale del supporto tecnico che gli utenti potrebbero visualizzare un banner di Office che richiede di riattivare le app di Office entro 72 ore dal cutover. </li><li>Tutte le applicazioni di Office nei computer personali devono essere chiuse e gli utenti devono disconnettersi e quindi accedere di nuovo. Nella barra di attivazione gialla, accedere per riattivare i servizi di Office 365.</li><li>I computer condivisi richiederanno azioni simili ai computer personali e non richiederanno una procedura speciale. </li><li>Nei dispositivi mobili, gli utenti devono disconnettersi dall'app, chiuderle e quindi accedere di nuovo.</li></ul>|
||||

## <a name="line-of-business-apps"></a>App line-of-business

Nel caso di app line-of-business, assicurati di aver completato la procedura preliminare per le app [line-of-business.](ms-cloud-germany-transition-add-pre-work.md#line-of-business-apps)

## <a name="office-services"></a>Servizi Office

L'ultimo servizio usato (MRU) in Office è un cutover dai servizi Microsoft Cloud Deutschland a Office 365 Global, non una migrazione. Solo i collegamenti MRU dal lato dei servizi globali di Office 365 saranno visibili dopo la migrazione dal Office.com portale. I collegamenti MRU da Microsoft Cloud Deutschland non sono visibili come collegamenti MRU nei servizi globali di Office 365. Nei servizi globali di Office 365, i collegamenti MRU sono accessibili solo dopo che la migrazione del tenant ha raggiunto la fase 9.

## <a name="post-migration"></a>Post-migrazione

Leggere l'articolo [attività post-migrazione](ms-cloud-germany-transition-add-experience.md#post-migration) ed eseguirle di conseguenza.

## <a name="more-information"></a>Ulteriori informazioni

Guida introduttiva:

- [Migrazione da Microsoft Cloud Deutschland ai servizi di Office 365 nelle nuove aree data center tedesche](ms-cloud-germany-transition.md)
- [Assistenza per la migrazione di Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Come acconsentire esplicitamente a eseguire la migrazione](ms-cloud-germany-migration-opt-in.md)
- [Esperienza del cliente durante la migrazione](ms-cloud-germany-transition-experience.md)

Passaggio attraverso la transizione:

- [Pre-lavoro aggiuntivo](ms-cloud-germany-transition-add-pre-work.md)
- Informazioni aggiuntive per [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivi,](ms-cloud-germany-transition-add-devices.md) [esperienze](ms-cloud-germany-transition-add-experience.md)e [ADFS.](ms-cloud-germany-transition-add-adfs.md)

App cloud:

- [Informazioni sul programma di migrazione di Dynamics 365](/dynamics365/get-started/migrate-data-german-region)
- [Informazioni sul programma di migrazione di Power BI](/power-bi/admin/service-admin-migrate-data-germany)
- [Guida introduttiva all'aggiornamento di Microsoft Teams](/microsoftteams/upgrade-start-here)
