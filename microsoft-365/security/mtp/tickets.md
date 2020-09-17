---
title: Integrazione dei ticket di ServiceNow nel centro sicurezza e conformità di Microsoft 365
description: Informazioni su come creare e registrare i ticket in ServiceNow dal centro sicurezza e conformità di Microsoft 365.
keywords: sicurezza, Microsoft 365, M365, conformità, centro conformità, Centro sicurezza, ServiceNow, ticket, attività, neve, connessione
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: b9e900baf02e9fc866fe6fe520ad1e40ccd565de
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950701"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a>Integrazione dei ticket di ServiceNow nel centro sicurezza e conformità di Microsoft 365

[!include[Prerelease information](../includes/prerelease.md)]

ServiceNow è una popolare piattaforma di cloud computing che aiuta le aziende a gestire i flussi di lavoro digitali per le operazioni aziendali. La piattaforma Now include i flussi di lavoro IT, i flussi di lavoro dei dipendenti e i flussi di lavoro del cliente. [Altre informazioni su ServiceNow](https://www.servicenow.com/)

Microsoft ha collaborato con ServiceNow per semplificare agli amministratori IT la gestione dei ticket e delle attività in entrambe le piattaforme. [Microsoft 365 Security Center](overview-security-center.md) e [Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) sono stati potenziati con la possibilità di creare e registrare in modo nativo i ticket in ServiceNow.

- [**Gestire i ticket di ServiceNow nel centro sicurezza**](tickets-security-center.md)
- **Gestire i ticket di ServiceNow nel centro conformità** (prossimamente)

## <a name="prerequisites"></a>Prerequisiti

Accedere al centro sicurezza e alla conformità di Microsoft 365 e a un'istanza di ServiceNow con:  

* Kingston o versione superiore
* Dispongono di credenziali di amministratore HI
* Disporre di privilegi di amministratore per l'istanza del fornitore di destinazione

ServiceNow consiglia agli utenti di mantenere le impostazioni predefinite nell'istanza di ServiceNow. L'utilizzo di personalizzazioni potrebbe causare errori durante il completamento dell'elenco di controllo di installazione e l'integrazione con Microsoft 365 Security Center.

## <a name="data-exchange"></a>Scambio di dati

Quando si connette Microsoft 365 Security Center o il centro conformità a ServiceNow, Microsoft riceve i dati aggiuntivi seguenti:

* Nome dell'istanza di ServiceNow
* ID client di ServiceNow
* Segreto client di ServiceNow
* Token di aggiornamento & di accesso di ServiceNow

Quando si crea un ticket di ServiceNow dal centro sicurezza Microsoft 365 o dal centro conformità, vengono inviati i dati seguenti a ServiceNow:

* ID utente che avvia la creazione del ticket
* Nome attività
* Descrizione attività
* Priority
* Data di scadenza
* Origine raccomandazione (raccomandazione utente o suggerimento Microsoft)
* Categoria di raccomandazione (dispositivi, dati, app, identità, infrastruttura)

## <a name="connect-to-servicenow"></a>Connettersi a ServiceNow

Per informazioni su come connettersi a ServiceNow, vedere [creare e monitorare i ticket di ServiceNow nel centro sicurezza Microsoft 365](tickets-security-center.md) . La connessione da Microsoft 365 Compliance Center è disponibile a breve.

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>Viene visualizzato un messaggio di errore nel primo passaggio dell'elenco di controllo per l'installazione (OAuth Creation)

**Messaggio di errore**: l'operazione di lettura su' oauth_entity ' dall'ambito ' x_mioms_m365ticket ' è stata rifiutata a causa del criterio di accesso cross-scope della tabella

L'app presuppone che qualsiasi amministratore nell'istanza di ServiceNow possa creare e leggere le entità OAuth. Questo errore potrebbe essere causato da una personalizzazione nell'istanza di ServiceNow che limita gli utenti autorizzati a creare o leggere le entità OAuth.

**ServiceNow consiglia agli utenti di mantenere la funzionalità predefinita.**

Impostare le configurazioni di tabella "registri applicazioni" su predefinita:

* Label = registri applicazioni
* Name = oauth_entity
* Accessibile da = tutti gli ambiti dell'applicazione
* È possibile selezionare la casella di controllo Leggi =

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>Come convalidare l'entità OAuth creata per Microsoft 365 Security & Compliance Connector

Andare alla tabella registri applicazioni (**Menu > System OAuth > Application Registry**) in ServiceNow. Individuare l'entità OAuth creata dall'utente, con il nome assegnato.

### <a name="signing-in-as-the-integration-user"></a>Accesso come utente di integrazione

Prima di autorizzare la connessione tra Microsoft 365 Security Center e ServiceNow, assicurarsi di utilizzare l'accesso dell'utente di integrazione e la password creata nei passaggi di installazione. Non utilizzare le credenziali personali.

1. Andare alla pagina autorizzazione in ServiceNow.
2. Se l'utente ha eseguito l'accesso con le proprie credenziali personali, selezionare il collegamento **che non si trova** nell'angolo in alto a destra.
3. Accedere a ServiceNow come utente di integrazione creato in precedenza nell'elenco di controllo di installazione.  
4. Selezionare **Consenti** nella pagina ServiceNow in cui viene chiesto se il connettore di sicurezza + conformità è in grado di connettersi all'account di ServiceNow.
5. Continuare con la procedura di installazione.

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a>Come convalidare l'utente di integrazione creato con l'elenco di controllo di installazione per Microsoft 365 Security & Compliance Connector

Andare alla tabella Users **(Menu > User Administration >** Users) in ServiceNow e trovare l'utente di integrazione creato da te, con il nome che l'hai assegnato.

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a>L'azienda dispone di accesso Single Sign-on che impedisce la connessione a ServiceNow tramite il Centro sicurezza di Microsoft 365

Se l'azienda ha abilitato l'accesso Single Sign-on e si riceve un errore o l'accesso non è riuscito, seguire una delle due soluzioni.

#### <a name="sign-in-to-servicenow-as-the-integration-user"></a>Accedere a ServiceNow come utente di integrazione

1. Tornare alla pagina autorizzazione in ServiceNow.
2. Selezionare il collegamento **not you** nell'angolo in alto a destra.
3. Accedere a ServiceNow come utente di integrazione creato in precedenza nell'elenco di controllo di installazione.  
4. Selezionare **Consenti** nella pagina ServiceNow in cui viene chiesto se il connettore di sicurezza + conformità è in grado di connettersi all'account di ServiceNow.
5. Continuare con la procedura di installazione.

#### <a name="create-a-security-admin-user"></a>Creare un utente di amministrazione della sicurezza

1. Creare un utente con privilegi di amministratore della sicurezza in Azure Active Directory. L'utente deve avere lo stesso nome e l'indirizzo di posta elettronica dell'utente di integrazione creato dall'elenco di controllo dell'installazione. È possibile rimuovere il ruolo di amministratore della protezione una volta che l'accesso e la connessione sono state completate.
2. Accedere al centro sicurezza Microsoft 365 come utente e seguire la procedura di installazione.

### <a name="ip-filtering"></a>Filtro IP

Se è stato abilitato il filtro IP, potrebbe essere necessario consentire esplicitamente gli indirizzi IP. Per informazioni su come consentire gli intervalli di indirizzi IP in ServiceNow, vedere [controllo di accesso all'indirizzo IP](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) . Vedere gli [intervalli e i tag di servizio di Azure IP-cloud pubblico](https://www.microsoft.com/en-us/download/details.aspx?id=56519) per un elenco di indirizzi IP da consentire.

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a>L'installazione è stata completata ma non è possibile visualizzare i ticket e non condividerli

Se i passaggi di installazione e installazione sono stati completati, ma non vengono visualizzate le schede di ServiceNow nella Home page e non è possibile condividere ServiceNow da Microsoft Secure score, controllare lo stato della pagina di provisioning in https://security.microsoft.com/ticketProvisioning . Selezionare **autorizza** e tornare alla Home page. Le schede devono essere visualizzate.

## <a name="resources"></a>Risorse

- [Gestire i ticket di ServiceNow nel centro sicurezza](tickets-security-center.md)