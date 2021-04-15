---
title: Ruoli di Azure Active Directory nell'interfaccia di amministrazione di Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: Gestisci questi ruoli di amministratore di Azure nell’interfaccia di amministrazione di Microsoft 365
ms.openlocfilehash: 72835a0f9fdf9a15fc3ffa07c0fab6ca6f0260cb
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759943"
---
# <a name="azure-active-directory-roles-in-the-microsoft-365-admin-center"></a>Ruoli di Azure Active Directory nell'interfaccia di amministrazione di Microsoft 365

L'interfaccia di amministrazione di Microsoft 365 consente di gestire più di 30 ruoli di Azure AD. Questi ruoli, tuttavia, sono un sottoinsieme dei ruoli disponibili nel portale di Azure. Se si ha un'azienda di grandi dimensioni, nel portale di Azure potrebbero essere presenti ruoli che soddisfano le esigenze dell'organizzazione. Per le descrizioni dettagliate dei ruoli di Azure AD, vedere [Autorizzazioni del ruolo di amministratore in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

Un utente a cui è assegnato un ruolo di amministratore avrà lo stesso livello di accesso a tutti i servizi cloud a cui è abbonata l'organizzazione, indipendentemente da come viene assegnato il ruolo, con l'interfaccia di amministrazione di Microsoft 365, nel portale di Azure o con il modulo di Azure AD per Windows PowerShell.

Nell'interfaccia di amministrazione di Microsoft 365 è possibile passare a **Ruoli** e quindi selezionare un ruolo per aprire il relativo riquadro dei dettagli. Selezionare la scheda **Autorizzazioni** per visualizzare l'elenco dettagliato delle autorizzazioni di cui dispongono gli amministratori a cui è assegnato quel ruolo. Selezionare la scheda **Assegnate** o **Amministratori assegnati** per aggiungere utenti ai ruoli. Per altre informazioni sull'assegnazione di ruoli nell'interfaccia di amministrazione di Microsoft 365, vedere [Assegnare ruoli di amministratore](assign-admin-roles.md).

## <a name="all-azure-ad-roles"></a>Tutti i ruoli di Azure AD

Ecco un elenco dei ruoli di amministratore disponibili nell'interfaccia di amministrazione di Microsoft 365. Cerchi le descrizioni dettagliate dei ruoli di amministratore di Microsoft 365? Vedere [Informazioni sui ruoli di amministratore](./about-admin-roles.md)

|Ruolo di amministratore     |Descrizione  |
|---------|---------|
|Amministratore di applicazioni     |    Ha accesso completo alle applicazioni aziendali, alle registrazioni delle applicazioni e alle impostazioni del proxy di applicazione.     |
|Sviluppatore applicazione     |    Può creare registrazioni di applicazioni e consentire l'accesso alle app per proprio conto.     |
|Amministratore autenticazione     |    Può richiedere agli utenti di registrare di nuovo l'autenticazione per le credenziali non di password, come AMF.     |
|Amministratore di Azure Information Protection     |   Gestisce le etichette per i criteri di Azure Information Protection, gestisce i modelli di protezione e attiva la protezione.       |
|Amministratore fatturazione     |    Effettua acquisti, gestisce gli abbonamenti e le richieste di servizio e monitora l'integrità dei servizi.     |
|Amministratore applicazione cloud     | Accesso completo alle applicazioni aziendali e alle registrazioni delle applicazioni. Nessun proxy di applicazione.     |
|Amministratore dispositivo cloud     |    Abilita, disabilita ed elimina i dispositivi e può leggere le chiavi BitLocker di Windows 10.     |
|Amministratore di conformità     |    Gestisce i requisiti normativi e i casi di eDiscovery, mantiene i criteri di governance dei dati per posizioni, identità e app.     |
|Amministratore dati di conformità     |    Tiene traccia dei dati, si assicura che siano protetti, ottiene informazioni dettagliate sui problemi e contribuisce ad attenuare i rischi.     |
|Amministratore accesso condizionale     |   Gestisce le impostazioni di accesso condizionale di Azure Active Directory, ma non i criteri di accesso condizionale di Exchange ActiveSync.      |
|Responsabile approvazione accesso a Customer Lockbox     |      Gestisce le richieste di Customer Lockbox e può attivare o disattivare Customer Lockbox.   |
|Amministratore di Desktop Analytics     |   Può accedere e gestire i servizi e gli strumenti di gestione di Desktop Analytics.      |
|Amministratore di Dynamics 365     |  Ha accesso completo a Microsoft Dynamics 365 Online, gestisce le richieste di servizio e monitora l'integrità dei servizi.       |
|Amministratore di Exchange     |  Ha accesso completo a Exchange Online, crea e gestisce gruppi, gestisce le richieste di servizio e monitora l'integrità dei servizi.    |
|Amministratore del provider di identità esterno    |     Configura i provider di identità per l'uso nella federazione diretta.    |
|Amministratore globale     |    Ha accesso illimitato a tutte le funzionalità di gestione e alla maggior parte dei dati in tutte le interfacce di amministrazione.     |
|Ruolo con autorizzazioni di lettura globali     |    Ha accesso in sola lettura a tutte le funzionalità di gestione e alla maggior parte dei dati nelle interfacce di amministrazione. Per una descrizione dettagliata dei diritti d'accesso e delle limitazioni di questo ruolo, vedere [Autorizzazioni del ruolo di amministratore in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader).    |
|Amministratore gruppi   |Crea gruppi e gestisce tutte le impostazioni dei gruppi nelle interfacce di amministrazione.|
|Mittente dell'invito guest     |    Gestisce gli inviti degli utenti guest di Azure Active Directory B2B.     |
|Amministratore di supporto tecnico     | Reimposta le password e le riautenticazioni per tutti gli utenti non amministratori e alcuni ruoli di amministratore, gestisce le richieste di servizio e monitora l'integrità dei servizi.      |
|Amministratore Insights     | Gestisce tutti gli aspetti di Microsoft 365 Insights, ossia legge le informazioni di Azure Active Directory, può monitorare l'integrità dei servizi e creare e gestire le richieste di servizio.      |
|Amministratore business Insights     | Leggere report e approfondimenti nell'applicazione Microsoft 365 Insights.      |
|Amministratore di Intune     | Ha accesso completo a Intune, gestisce utenti e dispositivi per l'associazione di criteri, crea e gestisce gruppi.      |
|Amministratore di Kaizala     |    Ha accesso completo a tutte le funzionalità e ai dati di gestione di Kaizala, gestisce le richieste di servizio.     |
|Amministratore licenze     |     Assegna e rimuove le licenze degli utenti e modifica la relativa posizione di utilizzo.    |
|Ruolo con autorizzazioni di lettura della privacy per il Centro messaggi     |    Accede ai messaggi sulla privacy dei dati nel Centro messaggi, riceve notifiche tramite posta elettronica.     |
|Ruolo con autorizzazioni di lettura per il Centro messaggi     | Legge e condivide i messaggi regolari nel Centro messaggi, riceve riepiloghi settimanali tramite posta elettronica, ha accesso in sola lettura a utenti, gruppi, domini e abbonamenti.     |
|Amministratore delle app di Office    |   Gestisce i criteri basati sul cloud per Office e i contenuti Novità che gli utenti vedono nelle app di Office.   |
|Amministratore password    |   Reimpostare le password di utenti non amministratori o membri dei ruoli seguenti: ruolo con autorizzazioni di lettura nella directory, mittente dell'invito guest, amministratore password. Questo ruolo non può concedere la capacità di gestire le richieste di servizio o monitorare l'integrità dei servizi.   |
|Amministratore di Power BI    |   Ha accesso completo alle attività di gestione di Power BI, gestisce le richieste di servizio e monitora l'integrità dei servizi.   |
|Amministratore di Power Platform     |    Ha accesso completo a Microsoft Dynamics 365, PowerApps, criteri di prevenzione della perdita dei dati e Microsoft Flow.     |
|Amministratore ruolo con privilegi     |    Gestisce le assegnazioni dei ruoli e tutte le funzionalità di controllo dell'accesso di Privileged Identity Management.     |
|Amministratore dell'autenticazione con privilegi     |    Reimposta le password, aggiorna le credenziali non di password, forza la disconnessione degli utenti, monitora l'integrità dei servizi e gestisce le richieste di servizio.     |
|Ruolo con autorizzazioni di lettura per i report     |   Legge i dati dei report sull'utilizzo della dashboard dei report, del pacchetto di contenuto di adozione di Power BI, dei report di accesso e dell'API di creazione report di Microsoft Graph.      |
|Amministratore della ricerca     |    Ha accesso completo a Microsoft Search, assegna i ruoli di amministratore della ricerca e editor della ricerca, gestisce i contenuti editoriali, monitora l'integrità dei servizi e crea richieste di servizio.     |
|Editor della ricerca     |    Può creare, modificare ed eliminare contenuti per Microsoft Search, come segnalibri, posizioni e domande e risposte.     |
|Amministratore della sicurezza     |    Controlla la sicurezza dell'organizzazione, gestisce i criteri di sicurezza, consulta le analisi e i report di sicurezza, monitora il panorama delle minacce.     |
|Operatore della sicurezza     |    Esamina e risponde agli avvisi di sicurezza, gestisce le funzionalità del Centro protezione identità, monitora l'integrità dei servizi.     |
|Ruolo con autorizzazioni di lettura per la sicurezza     |    Dispone dell'accesso in sola lettura alle funzionalità di sicurezza, ai report di accesso e ai log di controllo.     |
|Amministratore del supporto dei servizi     |    Crea richieste di servizio per i servizi Azure, Microsoft 365 e Office 365 e monitora l'integrità dei servizi.     |
|Amministratore di SharePoint     |    Ha accesso completo a SharePoint Online, gestisce i gruppi di Microsoft 365, gestisce le richieste di servizio e monitora l'integrità dei servizi.     |
|Amministratore di Skype for Business     | Ha accesso completo a tutte le funzionalità di Teams e Skype e agli attributi degli utenti di Skype, gestisce le richieste di servizio e monitora l'integrità dei servizi.      |
|Amministratore di Teams     |    Ha accesso completo all'interfaccia di amministrazione di Teams e Skype, gestisce richieste di servizio e gruppi di Microsoft 365 e monitora l'integrità dei servizi.     |
|Amministratore della comunicazione di Teams     |    Assegna i numeri di telefono, crea e gestisce i criteri vocali e delle riunioni e legge l'analisi delle chiamate.     |
|Tecnico del supporto delle comunicazioni di Teams     |    Legge i dettagli del registro chiamate per tutti i partecipanti per risolvere i problemi di comunicazione.     |
|Specialista del supporto delle comunicazioni di Teams     |    Legge i dettagli delle chiamate degli utenti solo per un utente specifico per risolvere i problemi di comunicazione.|
|Amministratore utenti     |   Reimposta le password utente, crea e gestisce utenti e gruppi, inclusi i filtri, gestisce le richieste di servizio e monitora l'integrità dei servizi.|

## <a name="delegated-administration-for-microsoft-partners"></a>Amministrazione con delega per partner Microsoft

Se si collabora con un partner Microsoft, è possibile assegnargli un ruolo di amministratore. Il partner a sua volta può assegnare un ruolo di amministratore ad altri utenti della propria azienda o di quella con cui collabora. Questo può essere utile, ad esempio, se al partner viene affidata la configurazione e la gestione dell'organizzazione online.
  
Un partner può assegnare questi ruoli:

- Amministrazione completa, con privilegi equivalenti a un amministratore globale, tranne la gestione dell'autenticazione a più fattori tramite il Centro per i partner.

- Amministrazione limitata: questo ruolo dispone di privilegi equivalenti a quelli del ruolo di amministratore di supporto tecnico.

Prima che il partner possa assegnare questi ruoli agli utenti, è necessario aggiungerlo come amministratore con delega al proprio account. Il processo viene avviato da un partner autorizzato, che invia un messaggio di posta elettronica nel quale richiede l'autorizzazione ad agire come amministratore con delega. Per istruzioni, vedere [Autorizzare o rimuovere relazioni con i partner](../misc/add-partner.md).
  
## <a name="related-articles"></a>Articoli correlati

[Informazioni sui ruoli di amministratore di Microsoft 365](about-admin-roles.md)

[Assegnare ruoli di amministratore](assign-admin-roles.md)
  
[Report sulle attività nell'interfaccia di amministrazione di Microsoft 365](../activity-reports/activity-reports.md)