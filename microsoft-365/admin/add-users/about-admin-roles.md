---
title: Informazioni sui ruoli di amministratore nell'interfaccia di amministrazione di Microsoft 365
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: da585eea-f576-4f55-a1e0-87090b6aaa9d
description: I ruoli di amministratore sono associati a funzioni aziendali e forniscono le autorizzazioni per eseguire determinate attività nell'interfaccia di amministrazione. Ad esempio, l'amministratore del servizio apre ticket di supporto presso Microsoft.
ms.custom: okr_smb
ms.openlocfilehash: 4e3cec5b2ff86b35d02f8963a584efdb272f2c5e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43618921"
---
# <a name="about-admin-roles"></a>Informazioni sui ruoli di amministratore

L'abbonamento include un set di ruoli di amministratore che possono essere assegnati a determinati utenti all'interno dell'organizzazione. Ogni ruolo di amministratore è associato a funzioni aziendali comuni e assegna le autorizzazioni per eseguire determinate attività nelle interfacce di amministrazione. Per ulteriori informazioni, vedere [Assegnare i ruoli di amministratore](assign-admin-roles.md).

> [!TIP] 
> Per le descrizioni dettagliate dei ruoli, vedere [Autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

## <a name="things-to-consider"></a>Aspetti da considerare

Dato che gli amministratori hanno accesso a file e dati sensibili, è consigliabile seguire queste linee guida per proteggere i dati dell'organizzazione.

| Consiglio                  | Perché è importante?                 |
| :------------------- | :------------------- |
| Avere da 2 a 4 amministratori globali  | Poiché solo un altro amministratore globale può reimpostare la password di un amministratore globale, è consigliabile la presenza di almeno 2 amministratori globali nell'organizzazione in caso di blocco dell'account. Tuttavia, siccome l'amministratore globale ha accesso quasi illimitato alle impostazioni dell'organizzazione e alla maggior parte dei dati, è consigliabile avere al massimo 4 amministratori globali per evitare rischi per la sicurezza. |
| Assegnare il ruolo *meno permissivo*    | Se si assegna il ruolo *meno permissivo*, gli amministratori avranno solo l'accesso di cui hanno bisogno per completare l'attività. Ad esempio, se si vuole che un qualcuno reimposti le password dei dipendenti, è meglio non assegnare il ruolo di amministratore globale illimitato, ma un ruolo di amministratore limitato, ad esempio amministratore password o di supporto tecnico. Questo contribuisce a proteggere i dati.                 |
| Richiedere l'autenticazione a più fattori per gli amministratori                  |    In realtà l'autenticazione a più fattori è consigliabile per tutti gli utenti, ma a maggior ragione per l'accesso degli amministratori dovrebbe essere un requisito imprescindibile. L'autenticazione a più fattori consente agli utenti di immettere un secondo metodo di identificazione per verificare la loro identità. Gli amministratori possono avere accesso a molti dati di clienti e dipendenti e, quando si applica l'autenticazione a più fattori, anche se la password dell'amministratore dovesse essere compromessa, sarebbe comunque inutilizzabile senza la seconda forma di identificazione.  <br><br>Quando si attiva l'autenticazione a più fattori, al successivo accesso l'utente dovrà specificare un indirizzo di posta elettronica alternativo e un numero di telefono per il ripristino dell'account.  <br> [Configurare l'autenticazione a più fattori](../security-and-compliance/set-up-multi-factor-authentication.md)          |

  
## <a name="some-roles-are-missing-from-active-users--manage-admin-roles-where-did-they-go"></a>Alcuni ruoli non sono più presenti in Utenti attivi > Gestire ruoli di amministratore. Dove sono finiti?
Per impostazione predefinita, vengono visualizzati i ruoli usati dalla maggior parte delle organizzazioni. Se non si riesce a trovare un ruolo, selezionare **Visualizza altri ruoli** in fondo all'elenco.

## <a name="how-can-i-tell-which-permissions-are-assigned-to-me"></a>Come si fa a stabilire di quali autorizzazioni si dispone?
Se nell'interfaccia di amministrazione viene visualizzato un messaggio che informa che non si hanno le autorizzazioni necessarie per modificare un'opzione o una pagina, è possibile che il ruolo di cui si dispone sia privo di tale autorizzazione.

## <a name="what-about-the-azure-active-directory-roles"></a>Informazioni sui ruoli di Azure Active Directory

Sul portale di Azure sono disponibili più ruoli rispetto all'interfaccia di amministrazione di Microsoft 365. Se si ha un'azienda di grandi dimensioni, nel portale di Azure potrebbero essere presenti ruoli che soddisfano le esigenze dell'organizzazione.

Per un elenco e una descrizione di tutti i ruoli di Azure Active Directory, vedere [Autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

Un utente a cui è assegnato un ruolo di amministratore avrà lo stesso livello di accesso a tutti i servizi cloud a cui è abbonata l'organizzazione, indipendentemente da come viene assegnato il ruolo, con l'interfaccia di amministrazione di Microsoft 365, nel portale di Azure o con il modulo di Azure AD per Windows PowerShell.
  
## <a name="roles-available-in-the-microsoft-365-admin-center"></a>Ruoli disponibili nell'interfaccia di amministrazione di Microsoft 365

L'interfaccia di amministrazione di Microsoft 365 consente di gestire più di 30 ruoli di Azure AD. Questi ruoli, tuttavia, sono un sottoinsieme dei ruoli disponibili nel portale di Azure.

::: moniker range="o365-worldwide"

Nell'interfaccia di amministrazione è possibile passare a **Ruoli** e quindi selezionare un ruolo per aprire il relativo riquadro dei dettagli. Selezionare la scheda **Autorizzazioni** per visualizzare l'elenco dettagliato delle autorizzazioni di cui dispongono gli amministratori a cui è assegnato quel ruolo.

::: moniker-end

Probabilmente sarà necessario assegnare solo i ruoli seguenti nell'organizzazione. Per informazioni dettagliate, inclusi i cmdlet associati a un ruolo, vedere [Autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

|Ruolo di amministratore     |A chi è opportuno assegnare questo ruolo?  |
|---------|---------|
|Amministratore di Exchange     |   Assegnare il ruolo di amministratore di Exchange agli utenti che hanno la necessità di visualizzare e gestire le cassette postali di posta elettronica degli utenti, i gruppi di Microsoft 365 ed Exchange Online. <br><br> Gli amministratori di Exchange possono anche:<br> - Recuperare gli elementi eliminati nella cassetta postale di un utente <br> - Configurare i delegati "Invia come"e "Invia per conto di" <br>  |
|Amministratore globale     |   Assegnare il ruolo di amministratore globale agli utenti che hanno bisogno dell'accesso globale alla maggior parte delle funzionalità di gestione e dei dati in Microsoft Online Services. <br><br> Concedere l'accesso globale a troppi utenti costituisce un rischio per la sicurezza; si consiglia di configurare tra 2 e 4 amministratori globali. <br><br> Solo gli amministratori globali possono:<br> - Reimpostare le password per tutti gli utenti <br> - Aggiungere e gestire domini <br> <br> **Nota:** la persona che ha effettuato l'iscrizione ai Microsoft Online Services diventa automaticamente un amministratore globale. |
|Ruolo con autorizzazioni di lettura globali    |   Assegnare il ruolo con autorizzazioni di lettura globali agli utenti che hanno l'esigenza di visualizzare funzionalità e impostazioni di amministrazione nelle interfacce di amministrazione che l'amministratore globale può visualizzare. L'amministratore con il ruolo con autorizzazioni di lettura globali non può modificare impostazioni.   |
|Amministratore gruppi     |   Assegna il ruolo di amministratore dei gruppi agli utenti che devono gestire tutte le impostazioni dei gruppi nelle interfacce di amministrazione, compresi l'interfaccia di amministrazione di Microsoft 365 e il portale di Azure Active Directory. <br><br> Gli amministratori dei gruppi possono:<br> - Creare, modificare, eliminare e ripristinare gruppi di Microsoft 365 <br> - Creare e aggiornare criteri per la creazione, la scadenza e la denominazione dei gruppi <br> - Creare, modificare, eliminare e ripristinare gruppi di sicurezza di Azure Active Directory| 
|Amministratore di supporto tecnico     |   Assegnare il ruolo di amministratore di supporto tecnico agli utenti che devono eseguire le azioni seguenti:<br> - Reimpostare password <br> - Forzare gli utenti a disconnettersi <br> - Gestire le richieste di servizio <br> - Monitorare l'integrità dei servizi <br> <br> **Nota**: l'amministratore di supporto tecnico può solo assistere gli utenti che non sono amministratori e gli utenti a cui sono assegnati i ruoli seguenti: ruolo con autorizzazioni di lettura nella directory, mittente dell'invito guest, amministratore di supporto tecnico, ruolo con autorizzazioni di lettura per il Centro messaggi e ruolo con autorizzazioni di lettura per i report.      |
|Amministratore delle app di Office    |   Assegnare il ruolo di amministratore delle app di Office agli utenti che devono eseguire le operazioni seguenti: <br> - Usare il servizio di criteri cloud di Office per creare e gestire i criteri basati su cloud per Office <br> - Creare e gestire richieste di servizio <br> - Gestire i contenuti "Novità" che gli utenti vedono nelle app di Office   <br> - Monitorare l'integrità dei servizi  |
|Amministratore del servizio    |   Assegnare il ruolo di amministratore del servizio come ruolo aggiuntivo agli amministratori o agli utenti che devono eseguire le operazioni seguenti, anche se non sono incluse nel loro ruolo: <br> - Aprire e gestire le richieste di servizio <br> - Visualizzare e condividere i post del Centro messaggi   |
|Amministratore di SharePoint    |   Assegnare il ruolo di amministratore di SharePoint agli utenti che devono accedere e gestire l'interfaccia di amministratore di SharePoint Online. <br><br>Gli amministratori di SharePoint possono anche: <br> -Creare ed eliminare siti <br> - Gestire raccolte siti e impostazioni globali di SharePoint   |
|Amministratore del servizio Teams    |   Assegnare il ruolo di amministratore del servizio Teams agli utenti che devono accedere e gestire l'interfaccia di amministratore di Teams. <br><br>Gli amministratori del servizio Teams possono anche svolgere le seguenti operazioni: <br> - Gestire riunioni <br> - Gestire i bridge di conferenza <br> - Gestire tutte le impostazioni a livello di organizzazione, inclusi federazione, aggiornamento di Teams e impostazioni del client Teams   |
|Amministratore utenti     |    Assegnare il ruolo di amministratore utenti agli utenti che devono eseguire le operazioni seguenti per tutti gli utenti: <br> - Aggiungere utenti e gruppi <br> - Assegnare licenze <br> -Gestire la maggior parte delle proprietà degli utenti <br> - Creare e gestire le visualizzazioni utente <br> - Aggiornare i criteri di scadenza delle password <br> - Gestire le richieste di servizio <br> - Monitorare l'integrità dei servizi <br><br>  L'amministratore utenti può eseguire le azioni seguenti anche per gli utenti che non sono amministratori e a cui è assegnato il ruolo con autorizzazioni di lettura nella directory, mittente dell'invito guest, amministratore di supporto tecnico, il ruolo con autorizzazioni di lettura per il Centro messaggi e il ruolo con autorizzazioni di lettura per i report: <br> - Gestire i nomi utente<br> - Eliminare e ripristinare utenti<br> - Reimpostare password <br> - Forzare gli utenti a disconnettersi <br> - Aggiornare le chiavi del dispositivo (FIDO)   |

### <a name="all-roles"></a>Tutti i ruoli

 Ecco un elenco dei ruoli di amministratore disponibili nell'interfaccia di amministrazione di Microsoft 365.

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
|Ruolo con autorizzazioni di lettura globali     |    Ha accesso in sola lettura a tutte le funzionalità di gestione e alla maggior parte dei dati nelle interfacce di amministrazione. Per una descrizione dettagliata dei diritti d'accesso e delle limitazioni di questo ruolo, vedere [Autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader).    |
|Amministratore gruppi   |Crea gruppi e gestisce tutte le impostazioni dei gruppi nelle interfacce di amministrazione.|
|Mittente dell'invito guest     |    Gestisce gli inviti degli utenti guest di Azure Active Directory B2B.     |
|Amministratore di supporto tecnico     | Reimposta le password e le riautenticazioni per tutti gli utenti non amministratori e alcuni ruoli di amministratore, gestisce le richieste di servizio e monitora l'integrità dei servizi.      |
|Amministratore di Intune     | Ha accesso completo a Intune, gestisce utenti e dispositivi per l'associazione di criteri, crea e gestisce gruppi.      |
|Amministratore di Kaizala     |    Ha accesso completo a tutte le funzionalità e ai dati di gestione di Kaizala, gestisce le richieste di servizio.     |
|Amministratore licenze     |     Assegna e rimuove le licenze degli utenti e modifica la relativa posizione di utilizzo.    |
|Ruolo con autorizzazioni di lettura della privacy per il Centro messaggi     |    Accede ai messaggi sulla privacy dei dati nel Centro messaggi, riceve notifiche tramite posta elettronica.     |
|Ruolo con autorizzazioni di lettura per il Centro messaggi     | Legge e condivide i messaggi regolari nel Centro messaggi, riceve riepiloghi settimanali tramite posta elettronica, ha accesso in sola lettura a utenti, gruppi, domini e abbonamenti.     |
|Amministratore delle app di Office    |   Gestisce i criteri basati sul cloud per Office e i contenuti Novità che gli utenti vedono nelle app di Office.   |
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

Prima che il partner possa assegnare questi ruoli agli utenti, è necessario aggiungerlo come amministratore con delega al proprio account. Il processo viene avviato da un partner autorizzato, che invia un messaggio di posta elettronica nel quale richiede l'autorizzazione ad agire come amministratore con delega. Per istruzioni, vedere [Autorizzare o rimuovere relazioni con i partner](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).
  
## <a name="related-articles"></a>Articoli correlati

[Assegnare ruoli di amministratore](assign-admin-roles.md)
  
[Report sulle attività nell'interfaccia di amministrazione di Microsoft 365](../activity-reports/activity-reports.md)
