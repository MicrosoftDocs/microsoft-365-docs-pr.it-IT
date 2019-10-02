---
title: Creare e monitorare i ticket tramite ServiceNow
description: Microsoft 365 Security Center è in fase di miglioramento grazie alla possibilità di creare e registrare in modo nativo i ticket in ServiceNow. In questo modo gli amministratori della sicurezza invieranno una raccomandazione di Punteggio sicuro direttamente a ServiceNow e creerà un ticket.
keywords: sicurezza, Microsoft 365, M365, Secure score, Centro sicurezza, ServiceNow, ticket, attività
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: b0b8cda81bb6cec3958e7b2a758da191d803a0ed
ms.sourcegitcommit: acf29701bfba3e4843e49a79fde012f3c7a7024a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "37350332"
---
# <a name="manage-tickets-through-servicenow"></a>Gestire i ticket tramite ServiceNow

Microsoft 365 Security Center è in fase di miglioramento grazie alla possibilità di creare e registrare in modo nativo i ticket in ServiceNow. Questo consente agli amministratori della sicurezza di inviare un'azione di miglioramento del [Punteggio di Microsoft Secure](microsoft-secure-score.md) direttamente a ServiceNow e di creare un ticket. È possibile creare sia la gestione degli incidenti che i ticket di gestione delle modifiche.

## <a name="prerequisites"></a>Prerequisiti

Accedere al centro sicurezza Microsoft 365 e a un'istanza di ServiceNow con:  

* Kingston o versione superiore
* Dispongono di credenziali di amministratore HI
* Disporre di privilegi di amministratore per l'istanza del fornitore di destinazione

ServiceNow consiglia agli utenti di tenere fuori dalle impostazioni della casella (impostazione predefinita) nell'istanza di ServiceNow.  L'utilizzo di personalizzazioni potrebbe causare errori durante il completamento dell'elenco di controllo di installazione e l'integrazione con Microsoft 365 Security Center.

## <a name="data-exchange"></a>Scambio di dati

Quando si connette Microsoft 365 Security Center a ServiceNow, Microsoft riceverà i seguenti dati aggiuntivi:

* Nome dell'istanza di ServiceNow
* ID client di ServiceNow
* Segreto client di ServiceNow
* Token di aggiornamento & di accesso di ServiceNow

Quando si crea un ticket ServiceNow dal centro sicurezza Microsoft 365, vengono inviati i dati seguenti a ServiceNow:

* ID utente che avvia la creazione del ticket
* Nome attività
* Descrizione attività
* Priority
* Data di scadenza
* Origine raccomandazione (raccomandazione utente o suggerimento Microsoft)
* Categoria di raccomandazione (dispositivi, dati, app, identità, infrastruttura)

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>Connettere il Centro sicurezza di Microsoft 365 a ServiceNow

Passare alla Home page del Centro sicurezza di Microsoft 365, dove verrà visualizzata una scheda che richiede se si utilizza ServiceNow.

![Si utilizza ServiceNow](../images/do-you-use-servicenow-250.png)

Da questa pagina verrà inviata la pagina di configurazione di ServiceNow in cui verranno seguite le istruzioni per autorizzare l'app del connettore Microsoft 365.

Quando si autorizza la connessione tra Microsoft 365 Security Center e ServiceNow, assicurarsi di utilizzare l'account di accesso e la password dell'utente di integrazione creati nei passaggi di installazione e non nelle credenziali personali.

Dopo aver seguito le istruzioni e aver autorizzato la connessione, è possibile visualizzare lo stato della connessione sia nella pagina connessione al centro sicurezza Microsoft 365 che nell'app ServiceNow di ticketing Connector di Microsoft 365. Ora è tutto pronto per iniziare a creare attività.

## <a name="create-a-task-and-share-it-to-servicenow"></a>Creare un'attività e condividerla con ServiceNow

Una volta configurata l'integrazione, è possibile creare attività di ServiceNow in base a specifiche azioni di miglioramento del Punteggio Microsoft sicuro. Andare a qualsiasi azione di miglioramento in Secure score nel portale Microsoft 365 Security Center e selezionare l'icona "Condividi". Una delle opzioni di menu a discesa è ServiceNow.

![Condivisione di ServiceNow in un punteggio sicuro](../images/servicenow-share.png)

Verrà quindi generata un'attività in cui è possibile impostare la priorità e modificare il nome, la descrizione o la data di scadenza. Una volta che tutti i campi richiesti sono stati riempiti, è possibile inviare l'attività a ServiceNow.

L'attività sarà visibile in ServiceNow come richiesta di modifica della sicurezza e della configurazione di Microsoft 365.

## <a name="track-tickets"></a>Registrare i ticket

Dopo aver creato i ticket per la gestione delle modifiche e la gestione degli incidenti di ServiceNow, verranno visualizzati nelle schede nella Home page del Centro sicurezza Microsoft 365. Da queste schede, è possibile creare un ticket, visualizzare tutti i ticket o gestire la configurazione di ServiceNow.

![Ticket di gestione delle modifiche di ServiceNow](../images/change-management-375.png)  ![Ticket per la gestione degli incidenti di ServiceNow](../images/incident-management-375.png)

Per eseguire il provisioning o la gestione dell'integrazione di ServiceNow nel centro sicurezza Microsoft 365, selezionare **Gestisci configurazione ServiceNow** su una delle schede. Da qui è possibile rimuovere la connessione ServiceNow corrente e personalizzare i nomi dei ticket dello stato.

Con i ticket di ServiceNow visibili nel centro sicurezza Microsoft 365, le attività vivranno in un luogo in cui possono essere monitorate e attivate insieme agli altri elementi del dashboard di sicurezza.

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="i-am-receiving-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>Sto ricevendo un errore nel primo passaggio dell'elenco di controllo di installazione (OAuth Creation)

**Messaggio di errore**: l'operazione di lettura su' oauth_entity ' dall'ambito ' x_mioms_m365ticket ' è stata rifiutata a causa del criterio di accesso cross-scope della tabella

La nostra app presuppone che qualsiasi amministratore nell'istanza di ServiceNow possa creare e leggere le entità OAuth. Questo errore potrebbe essere causato da una personalizzazione dell'istanza di ServiceNow, che limita gli utenti autorizzati a creare/leggere le entità OAuth. ServiceNow consiglia agli utenti di tenere fuori dalla funzionalità box (impostazione predefinita).

Impostare le configurazioni di tabella "registri applicazioni" su predefinita:

* Label = registri applicazioni
* Name = oauth_entity
* Accessibile da = tutti gli ambiti dell'applicazione
* È possibile selezionare la casella di controllo Leggi =

**ServiceNow consiglia agli utenti di tenere fuori dalla funzionalità box (impostazione predefinita).**

### <a name="how-do-i-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>Come convalidare l'entità OAuth creata per Microsoft 365 Security & Compliance Connector?

Andare alla tabella registri applicazioni (menu > System OAuth > Application Registry) in ServiceNow e individuare l'entità OAuth creata dall'utente (nome assegnato).

### <a name="how-do-i-validate-the-integration-user-created-in-step-two-of-installation-checklist-for-microsoft-365-security--compliance-connector"></a>Come convalidare l'utente di integrazione creato nel passaggio 2 dell'elenco di controllo di installazione per Microsoft 365 Security & Compliance Connector?

Andare alla tabella users (menu > User Administration > Users) in ServiceNow e trovare l'utente di integrazione creato da voi (nome che è stato assegnato).

Quando si autorizza la connessione tra Microsoft 365 Security Center e ServiceNow, assicurarsi di utilizzare l'account di accesso e la password dell'utente di integrazione creati nei passaggi di installazione e non nelle credenziali personali.

### <a name="i-have-completed-the-installation-and-set-up-steps-but-i-am-unable-to-see-the-servicenow-cards-on-the-home-page-and-cannot-see-the-share-icon-in-microsoft-secure-score"></a>Sono state completate le operazioni di installazione e configurazione, ma non sono in grado di visualizzare le schede di ServiceNow nella Home page e non è possibile visualizzare l'icona Condividi in Microsoft Secure Score

Controllare lo stato della pagina di provisioning accedendo a https://security.microsoft.com/ticketProvisioning. Selezionare **Salva** e torna alla Home page. Le schede devono essere visualizzate.
