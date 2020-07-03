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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: da585eea-f576-4f55-a1e0-87090b6aaa9d
description: I ruoli di amministratore sono associati a funzioni aziendali e forniscono le autorizzazioni per eseguire determinate attività nell'interfaccia di amministrazione. Ad esempio, l'amministratore del servizio apre ticket di supporto presso Microsoft.
ms.openlocfilehash: e76024f1d13e9210b74e2f6c4fc63c9992615099
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015912"
---
# <a name="about-admin-roles"></a>Informazioni sui ruoli di amministratore

L'abbonamento a Microsoft 365 o Office 365 include un set di ruoli di amministratore che possono essere assegnati a determinati utenti all'interno dell'organizzazione tramite l'interfaccia di amministrazione di Microsoft 365. Ogni ruolo di amministratore è associato a funzioni aziendali comuni e assegna le autorizzazioni per eseguire determinate attività nelle interfacce di amministrazione.

L'interfaccia di amministrazione di Microsoft 365 consente di gestire i ruoli di Azure Active Directory e i ruoli di Microsoft Intune. Questi ruoli, tuttavia, sono un sottoinsieme dei ruoli disponibili nel portale di Azure AD e nell'interfaccia di amministrazione di Intune.

Per le descrizioni dettagliate dei ruoli di Azure AD che è possibile gestire nell'interfaccia di amministrazione di Microsoft 365, vedere l'articolo sulle autorizzazioni del ruolo di amministratore in Azure Active Directory. [Autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

Per le descrizioni dettagliate dei ruoli di Intune che è possibile gestire nell'interfaccia di amministrazione di Microsoft 365,  vedere [Controllo degli accessi in base al ruolo con Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).

Per altre informazioni sull'assegnazione di ruoli nell'interfaccia di amministrazione di Microsoft 365, vedere [Assegnare ruoli di amministratore](assign-admin-roles.md).

## <a name="security-guidelines-for-assigning-roles"></a>Linee guida di sicurezza per l'assegnazione di ruoli

Dato che gli amministratori hanno accesso a file e dati sensibili, è consigliabile seguire queste linee guida per proteggere i dati dell'organizzazione.

| Consiglio                  | Perché è importante?                 |
| :------------------- | :------------------- |
| Avere da 2 a 4 amministratori globali  | Poiché solo un altro amministratore globale può reimpostare la password di un amministratore globale, è consigliabile la presenza di almeno 2 amministratori globali nell'organizzazione in caso di blocco dell'account. Tuttavia, siccome l'amministratore globale ha accesso quasi illimitato alle impostazioni dell'organizzazione e alla maggior parte dei dati, è consigliabile avere al massimo 4 amministratori globali per evitare rischi per la sicurezza. |
| Assegnare il ruolo *meno permissivo*    | Se si assegna il ruolo *meno permissivo*, gli amministratori avranno solo l'accesso di cui hanno bisogno per completare l'attività. Ad esempio, se si vuole che un qualcuno reimposti le password dei dipendenti, è meglio non assegnare il ruolo di amministratore globale illimitato, ma un ruolo di amministratore limitato, ad esempio amministratore password o di supporto tecnico. Questo contribuisce a proteggere i dati.                 |
| Richiedere l'autenticazione a più fattori per gli amministratori                  |    In realtà l'autenticazione a più fattori è consigliabile per tutti gli utenti, ma a maggior ragione per l'accesso degli amministratori dovrebbe essere un requisito imprescindibile. L'autenticazione a più fattori consente agli utenti di immettere un secondo metodo di identificazione per verificare la loro identità. Gli amministratori possono avere accesso a molti dati di clienti e dipendenti e, quando si applica l'autenticazione a più fattori, anche se la password dell'amministratore dovesse essere compromessa, sarebbe comunque inutilizzabile senza la seconda forma di identificazione.  <br><br>Quando si attiva l'autenticazione a più fattori, al successivo accesso l'utente dovrà specificare un indirizzo di posta elettronica alternativo e un numero di telefono per il ripristino dell'account.  <br> [Configurare l'autenticazione a più fattori](../security-and-compliance/set-up-multi-factor-authentication.md)          |

Se nell'interfaccia di amministrazione viene visualizzato un messaggio che informa che non si hanno le autorizzazioni necessarie per modificare un'opzione o una pagina, è possibile che il ruolo di cui si dispone sia privo di tale autorizzazione.

## <a name="commonly-used-microsoft-365-admin-center-roles"></a>Ruoli dell'interfaccia di amministrazione di Microsoft 365 di uso comune

::: moniker range="o365-worldwide"

Nell'interfaccia di amministrazione di Microsoft 365 è possibile passare a **Ruoli** e quindi selezionare un ruolo per aprire il relativo riquadro dei dettagli. Selezionare la scheda **Autorizzazioni** per visualizzare l'elenco dettagliato delle autorizzazioni di cui dispongono gli amministratori a cui è assegnato quel ruolo. Selezionare la scheda **Assegnate** o **Amministratori assegnati** per aggiungere utenti ai ruoli.

::: moniker-end

Probabilmente sarà necessario assegnare solo i ruoli seguenti nell'organizzazione. Per impostazione predefinita, vengono visualizzati i ruoli usati dalla maggior parte delle organizzazioni. Se non si riesce a trovare un ruolo, selezionare **Visualizza altri ruoli** in fondo all'elenco. Per informazioni dettagliate, inclusi i cmdlet associati a un ruolo, vedere [Autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

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

## <a name="delegated-administration-for-microsoft-partners"></a>Amministrazione con delega per partner Microsoft

Se si collabora con un partner Microsoft, è possibile assegnargli un ruolo di amministratore. Il partner a sua volta può assegnare un ruolo di amministratore ad altri utenti della propria azienda o di quella con cui collabora. Questo può essere utile, ad esempio, se al partner viene affidata la configurazione e la gestione dell'organizzazione online.
  
Un partner può assegnare questi ruoli:
  
- **Amministrazione completa** Privilegi equivalenti a un amministratore globale, tranne la gestione dell'autenticazione a più fattori tramite il Centro per i partner.

- **Amministrazione limitata** Privilegi equivalenti a quelli del ruolo di amministratore di supporto tecnico.

Prima che il partner possa assegnare questi ruoli agli utenti, è necessario aggiungerlo come amministratore con delega al proprio account. Il processo viene avviato da un partner autorizzato, che invia un messaggio di posta elettronica nel quale richiede l'autorizzazione ad agire come amministratore con delega. Per istruzioni, vedere [Autorizzare o rimuovere relazioni con i partner](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).
  
## <a name="related-articles"></a>Articoli correlati

[Assegnare ruoli di amministratore](assign-admin-roles.md)

[Ruoli di Azure AD nell'interfaccia di amministrazione di Microsoft 365](azure-ad-roles-in-the-mac.md)

[Ruolo di amministratore di Exchange Online](about-exchange-online-admin-role.md)
  
[Report sulle attività nell'interfaccia di amministrazione di Microsoft 365](../activity-reports/activity-reports.md)
