---
title: Fasi di migrazione azioni e impatti per la migrazione da Microsoft Cloud Deutschland (generale)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
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
description: 'Riepilogo: informazioni sulle fasi di migrazione azioni e impatto del passaggio da Microsoft Cloud Germany (Microsoft Cloud Deutschland) a Office 365 Services nella nuova area del datacenter tedesco.'
ms.openlocfilehash: 4a032ab88704cfb46b3f451d939a784d222cbb40
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688630"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>Fasi di migrazione azioni e impatti per la migrazione da Microsoft Cloud Deutschland (generale)

Le migrazioni tenant da Microsoft Cloud Deutschland all'area Germania dei servizi Microsoft Office 365 vengono eseguite come un insieme di azioni configurate per ogni carico di lavoro. Queste azioni garantiscono che i dati e le esperienze critiche vengano migrati nei servizi di Office 365. Dopo aver aggiunto il tenant alla coda di migrazione, ogni carico di lavoro verrà completato come un insieme di passaggi eseguiti nel servizio back-end. Alcuni carichi di lavoro possono richiedere operazioni dall'amministratore (o dall'utente) oppure la migrazione può influire sull'utilizzo per le fasi eseguite e discusse in [come è organizzata la migrazione?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

Nelle sezioni seguenti sono contenute azioni ed effetti per i carichi di lavoro durante l'esecuzione di varie fasi della migrazione. Esaminare le tabelle e determinare quali azioni o effetti sono applicabili alla propria organizzazione. Assicurarsi di essere pronti a eseguire la procedura nelle rispettive fasi come richiesto. La mancata esecuzione dei passaggi necessari può causare un'interruzione del servizio e potrebbe ritardare il completamento della migrazione ai servizi di Office 365.

## <a name="exchange-online"></a>Exchange Online

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| La nuova area di Germania viene aggiunta alla configurazione dell'organizzazione esistente e le cassette postali vengono spostate in Office 365 Services. | La configurazione di Exchange Online aggiunge la nuova area tedesca di go-local all'organizzazione di transizione. Questa area di servizi di Office 365 è impostata come predefinita, consentendo al servizio di bilanciamento del carico interno di ridistribuire le cassette postali nell'area predefinita appropriata in Office 365 Services. In questa transizione, gli utenti di entrambi i lati (Germania o Office 365 Services) si trovano nella stessa organizzazione e possono utilizzare l'endpoint URL. | Exchange Online | -Transizione degli utenti e dei servizi dagli URL Germania agli URL dei servizi di Office 365 ( `https://outlook.office365.com` ). <br><br> -Gli utenti continueranno ad accedere al servizio tramite gli URL legacy Germany durante la migrazione. Non è necessaria alcuna azione immediata. <br><br> -Gli utenti devono iniziare a utilizzare il portale di office.com per le funzionalità di Office Online (calendario, posta elettronica, persone). L'esplorazione dei servizi che non sono ancora stati migrati nei servizi di Office 365 non funzionerà fino alla migrazione. <br><br> -Outlook Web App non fornisce l'esperienza delle cartelle pubbliche durante la migrazione. |
|||||

Considerazioni aggiuntive:

- `myaccount.msft.com` funzionerà solo dopo l'completa di Office 365. I collegamenti produrranno messaggi di errore "qualcosa è andato storto" fino a quel momento.

- Gli utenti di Outlook Web App che accedono a una cassetta postale condivisa nell'altro ambiente (ad esempio, un utente dell'ambiente Germany che accede a una cassetta postale condivisa nell'ambiente globale) verranno invitati a eseguire l'autenticazione una seconda volta. L'utente deve innanzitutto autenticare e accedere alla propria cassetta postale `outlook.office.de` , quindi aprire la cassetta postale condivisa `outlook.office365.com` . Sarà necessario eseguire l'autenticazione una seconda volta quando si accede alle risorse condivise ospitate nell'altro servizio.

- Per i clienti Microsoft Cloud Deutschland esistenti o quelli in fase di transizione, quando una cassetta postale condivisa viene aggiunta a Outlook utilizzando **File > Info > Aggiungi account**, la visualizzazione delle autorizzazioni del calendario potrebbe non riuscire (il client di Outlook tenta di utilizzare l'API REST `https://outlook.office.de/api/v2.0/Me/Calendars` ). I clienti che desiderano aggiungere un account per visualizzare le autorizzazioni del calendario possono aggiungere la chiave del registro di sistema, come descritto in [modifiche dell'esperienza utente per la condivisione di un calendario in Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) per garantire che questa azione abbia esito positivo. Questa chiave del registro di sistema può essere distribuita a livello di organizzazione tramite criteri di gruppo.

- Durante la fase di migrazione, l'utilizzo dei cmdlet di PowerShell **New-migrationEndpoint**, **set-migrationEndpoint** e **test-MigrationsServerAvailability** può causare errori (errore sul proxy). Questo accade quando la cassetta postale di arbitraggio ha eseguito la migrazione in tutto il mondo, ma la cassetta postale di amministrazione non ha o viceversa. Per risolvere questo passaggio, durante la creazione della sessione tenant di PowerShell, utilizzare la cassetta postale di arbitraggio come suggerimento per il routing in **ConnectionURI**. Ad esempio: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- Se si utilizza Exchange Online ibrido:

    - È necessario rieseguire la procedura guidata di configurazione ibrida (HCW) per aggiornare la configurazione locale a Microsoft Cloud Deutschland prima della transizione e rieseguire HCW al momento della pulizia nei servizi di Office 365. Se si utilizzano domini personalizzati, potrebbe essere necessario un aggiornamento DNS aggiuntivo.

Per ulteriori informazioni sulle differenze per le organizzazioni nella migrazione e dopo la migrazione delle risorse di Exchange Online, esaminare le informazioni in [Customer Experience durante la migrazione a Office 365 Services nelle nuove aree del datacenter tedesco](ms-cloud-germany-transition-experience.md).

## <a name="exchange-online-protection"></a>Exchange Online Protection

Le funzionalità di Exchange Online Protection (EOP) back-end vengono copiate nella nuova area di Germania. 

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Migrazione del routing di Exchange Online e del dettaglio dei messaggi cronologici. | Exchange Online consente di instradare gli host esterni a Office 365. I record MX esterni vengono inoltrati in modo da instradare il servizio EOP. Vengono migrate la configurazione tenant e i dettagli cronologici. | Clienti di Exchange Online | -Microsoft: le voci DNS gestite vengono aggiornate da Office 365 Germany EOP ai servizi di Office 365. <br><br> -I clienti devono attendere 30 giorni dopo EOP Dual Write per la migrazione di EOP. In caso contrario, potrebbe verificarsi una perdita di dati. |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| SharePoint e OneDrive vengono transizione. | SharePoint e OneDrive vengono migrati da Microsoft Cloud Deutschland a Office 365 Services in questa fase. Gli URL esistenti di Microsoft Cloud Deutschland sono conservati (ad esempio, `contoso.sharepoint.de` ). I token emessi da Microsoft Cloud Deutschland o Office 365 Services sono validi durante la transizione. | Clienti di SharePoint | -Il contenuto sarà di sola lettura per due brevi periodi durante la migrazione. Durante questo periodo, si prevede un banner "non è possibile modificare il contenuto" in SharePoint. <br><br> -L'indice di ricerca non verrà conservato e potrebbe richiedere fino a 10 giorni per la ricostruzione. <br><br> -Il contenuto di SharePoint/OneDrive sarà di sola lettura per due brevi periodi durante la migrazione. Gli utenti visualizzeranno brevemente un banner "non è possibile modificare il contenuto" durante questo periodo. <br><br> -L'indice di ricerca potrebbe non essere disponibile mentre l'indice viene ricompilato. Durante questo periodo, le query di ricerca potrebbero non restituire risultati completi. <br><br> -I siti esistenti vengono mantenuti. |
|||||

Considerazioni aggiuntive:

- Dopo aver completato la migrazione di SharePoint Online all'area tedesca, vengono ricreati gli indici dei dati. Le caratteristiche che dipendono dagli indici di ricerca possono essere intaccate durante la reindicizzazione completa.

- Se l'organizzazione utilizza ancora flussi di lavoro di SharePoint 2010, non funzionerà più dopo il 31 dicembre 2021. I flussi di lavoro di SharePoint 2013 rimarranno supportati, sebbene disattivati per impostazione predefinita per i nuovi tenant a partire dal 1 ° novembre 2020. Dopo aver completato la migrazione al servizio SharePoint Online, è consigliabile passare a Power automatizzate o ad altre soluzioni supportate.

- Dopo il completamento della migrazione di OneDrive all'area tedesca, vengono ricompilati gli indici di dati. Le caratteristiche che dipendono dagli indici di ricerca potrebbero essere intaccate durante la reindicizzazione.


## <a name="skype-for-business-online"></a>Skype for Business Online

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Migrazione di Skype for business a teams. | I clienti Skype for business esistenti vengono migrati nei servizi di Office 365 in Europa e quindi trasferiti a Microsoft teams nell'area Germania dei servizi di Office 365. | Clienti Skype for business | -Gli utenti non saranno in grado di accedere a Skype for business nella data di migrazione. Dieci giorni prima della migrazione, notificheremo gli utenti finali tramite il client Skype for business in banda, che verranno aggiornati ai team. Dopo 10 giorni verrà eseguita anche l'interfaccia di amministrazione. <br><br> -Viene eseguita la migrazione della configurazione del criterio. <br><br> -Gli utenti saranno migrati a squadre e non avranno più Skype for business dopo la migrazione. <br><br> -Gli utenti devono avere installato il client desktop teams. L'installazione avverrà nei 10 giorni tramite Policy sull'infrastruttura Skype for business, ma, in caso di esito negativo, gli utenti dovranno comunque scaricare il client o connettersi con un browser supportato. <br><br> -I contatti e le riunioni verranno migrati a squadre. <br><br> -Gli utenti non saranno in grado di accedere a Skype for business tra le transizioni di servizio di tempo e i servizi di Office 365 e non finché non verranno completate le voci DNS del cliente. <br><br> -I contatti e le riunioni esistenti continueranno a funzionare come riunioni di Skype for business. |
|||||

## <a name="office-services"></a>Servizi di Office

Il servizio utilizzato più di recente (MRU) in Office è un completa dal servizio Germany ai servizi di Office 365, non una migrazione. Solo i collegamenti MRU provenienti dal fianco dei servizi di Office 365 saranno visibili dopo la migrazione dal portale Office.com. I collegamenti MRU provenienti dal servizio Germany non sono visibili come collegamenti MRU nei servizi di Office 365. In Office 365, i collegamenti MRU sono accessibili solo dopo che la migrazione del tenant è stata completata.

## <a name="subscription"></a>Abbonamento

| Passaggi | Descrizione | Si applica a | Impatto |
|:-------|:-----|:-------|:-------|
| Non è possibile eseguire la migrazione dei clienti senza consenso. | Microsoft acquisisce il diritto di eseguire la migrazione in uno dei due modi, che consente a Microsoft di orchestrare la transizione di dati e servizi all'istanza di servizi di Office 365. <br> L'amministratore sceglie di eseguire la migrazione basata su Microsoft. <br> I clienti rinnovano gli abbonamenti nel loro tenant Microsoft Cloud Deutschland dopo il 1 ° maggio 2020. Notificheremo a questi clienti del diritto di migrazione ogni mese, attendere 30 giorni per offrire ai clienti la possibilità di annullare e quindi scegliere direttamente in ICM. | Tutti i clienti di Office | -Tenant è contrassegnato come acconsentito per la migrazione e l'interfaccia di amministrazione Visualizza la conferma. <br><br> -Il riconoscimento viene inviato al tenant del centro messaggi Cloud Germany. La configurazione del servizio continua dagli endpoint di Microsoft Cloud Deutschland. <br><br> -Monitorare il centro messaggi per gli aggiornamenti sullo stato delle fasi di migrazione. |
| Le sottoscrizioni vengono trasferite e le licenze vengono riassegnate. | Dopo la transizione del tenant ai servizi di Office 365, le sottoscrizioni corrispondenti ai servizi di Office 365 sono state acquistate per gli abbonamenti Microsoft Cloud Deutschland trasferiti. Agli utenti con licenze Microsoft Cloud Deutschland assegnate verranno assegnate le licenze per i servizi di Office 365. Gli abbonamenti legacy di Microsoft Cloud Deutschland sono stati rimossi dal tenant dei servizi di Office 365 al termine dell'esecuzione. | Tutti i clienti di Office | -Le modifiche apportate agli abbonamenti esistenti verranno bloccate (ad esempio, nessun nuovo acquisto di sottoscrizione o modifiche del numero di sede) durante questa fase. <br><br> -Le modifiche dell'assegnazione delle licenze verranno bloccate. <br><br> -La sottoscrizione di Microsoft Cloud Deutschland verrà migrata alla corrispondente sottoscrizione dei servizi di Office 365. L'offerta per i servizi di Office 365 di tale sottoscrizione è definita da Microsoft (nota anche come _mapping di offerta_). <br><br> -Il numero di funzionalità (piani di servizio) offerti dai servizi di Office 365 può essere superiore all'offerta originale di Microsoft Cloud Deutschland. Le licenze utente nei servizi di Office 365 verranno assegnate a simili caratteristiche di Microsoft Cloud Deutschland (piani di servizio). Le licenze utente di tutti gli utenti verranno assegnate automaticamente alle nuove funzionalità. L'amministratore deve intraprendere un'azione esplicita per disabilitare tali licenze, se necessario. <br><br> -Al termine della migrazione della sottoscrizione, sia i servizi di Office 365 che gli abbonamenti in Germania saranno visibili nel portale di amministrazione di Office 365, con lo stato degli abbonamenti Germania come _deprovisioned_. <br><br> -Gli utenti saranno riassegnati le licenze che sono legate alle nuove sottoscrizioni dei servizi di Office 365. Tutti i processi dei clienti che hanno dipendenze da abbonamenti o GUID SKU in Germania saranno interrotti e dovranno essere modificati con l'offerta di servizi di Office 365. <br><br> -Le nuove sottoscrizioni nei servizi di Office 365 verranno acquistate con il nuovo termine (mensile/trimestrale/annuale) e il cliente riceverà un rimborso proporzionale per il saldo inutilizzato dell'abbonamento a Microsoft Cloud Deutschland. <br><br> -Partner Microsoft Cloud Deutschland i tenant non verranno migrati. I clienti CSP verranno migrati ai servizi di Office 365 sotto il nuovo tenant dei servizi di Office 365 dello stesso partner. Dopo la migrazione dei clienti, il partner può gestire il cliente solo dal tenant dei servizi di Office 365. <br><br> -Sono disponibili altre funzionalità, ad esempio Microsoft Planner e Microsoft Flow, a meno che non vengano disabilitate dall'amministratore del tenant. Per informazioni su come disabilitare i piani di servizio assegnati alle licenze degli utenti, vedere [Disable access to Microsoft 365 Services while assigning User licenses](disable-access-to-services-while-assigning-user-licenses.md).  |
|||||

## <a name="next-step"></a>Passaggio successivo

[Eseguire ulteriori operazioni di prelavoro](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>Altre informazioni

Guida introduttiva:

- [Migrazione da Microsoft Cloud Deutschland a Office 365 Services nelle nuove aree del datacenter tedesco](ms-cloud-germany-transition.md)
- [Assistenza per la migrazione di Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Come acconsentire esplicitamente a eseguire la migrazione](ms-cloud-germany-migration-opt-in.md)
- [Esperienza del cliente durante la migrazione](ms-cloud-germany-transition-experience.md)

Spostamento attraverso la transizione:

- [Ulteriore prelavoro](ms-cloud-germany-transition-add-pre-work.md)
- Ulteriori informazioni su [Azure ad](ms-cloud-germany-transition-azure-ad.md), [dispositivi](ms-cloud-germany-transition-add-devices.md), [esperienze](ms-cloud-germany-transition-add-experience.md)e [ad FS](ms-cloud-germany-transition-add-adfs.md).

App Cloud:

- [Informazioni sul programma di migrazione di Dynamics 365](https://aka.ms/d365ceoptin)
- [Informazioni sul programma di migrazione di Power BI](https://aka.ms/pbioptin)
- [Guida introduttiva all'aggiornamento di Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
