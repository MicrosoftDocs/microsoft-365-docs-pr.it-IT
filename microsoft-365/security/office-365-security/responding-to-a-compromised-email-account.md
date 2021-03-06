---
title: Rispondere a un account di posta elettronica compromesso
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection:
- o365_security_incident_response
- M365-security-compliance
- m365solution-smb
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
localization_priority: Priority
search.appverid:
- MET150
description: Informazioni su come riconoscere e rispondere a un account di posta elettronica compromesso usando gli strumenti disponibili in Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 090253806295d0a5db67afbe769c9c0ca8be4b39
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054337"
---
# <a name="responding-to-a-compromised-email-account"></a>Rispondere a un account di posta elettronica compromesso

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Riepilogo** Informazioni su come riconoscere e rispondere a un account di posta elettronica compromesso in Microsoft 365.

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a>Che cos'è un account di posta elettronica compromesso in Microsoft 365?

L'accesso alle cassette postali, dati e altri servizi di Microsoft 365 viene controllato tramite l'uso di credenziali, ad esempio un nome utente e la password o il PIN. Quando un utente diverso da quello previsto sottrae queste credenziali, queste sono considerate compromesse. Con queste l'utente malintenzionato può accedere come utente originale ed effettuare operazioni illegali.

Usando le credenziali rubate, l'autore dell'attacco può accedere alla cassetta postale di Microsoft 365, alle cartelle di SharePoint o ai file in OneDrive dell'utente. Un’operazione vista comunemente è l’invio da parte del pirata informatico di messaggi di posta elettronica a destinatari sia interni che esterni all'organizzazione dell'utente originale. Quando un utente malintenzionato invia dei dati tramite messaggi di posta elettronica a destinatari esterni, si chiama esfiltrazione di dati.

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a>Sintomi di un account di posta elettronica Microsoft compromesso

Gli utenti potrebbero notare e segnalare attività insolite nelle proprie cassette postali di Microsoft 365. Seguono alcuni sintomi comuni:

- Attività sospette, ad esempio messaggi di posta elettronica mancanti o eliminati.
- Altri utenti potrebbero ricevere messaggi di posta elettronica dall'account compromesso senza che sia presente il messaggio di posta elettronica corrispondente nella cartella **Posta inviata** del mittente.
- La presenza di regole posta in arrivo che non sono state create dal proprietario o dall'amministratore. Queste regole possono inoltrare messaggi di posta elettronica a indirizzi sconosciuti o spostarli automaticamente nelle cartelle di **Note**, **Posta indesiderata**, o **Sottoscrizioni RSS**.
- Il nome visualizzato dell'utente può essere modificato nell'elenco indirizzi globale.
- Non è possibile inviare messaggi di posta elettronica dalla cassetta postale dell'utente.
- Le cartelle Posta inviata o Posta eliminata in Microsoft Outlook o Outlook sul web (precedentemente noto come Outlook Web App) contengono messaggi presenti comunemente in un account oggetto di un attacco, ad esempio "Mi sono bloccato a Milano, invia denaro."
- Modifiche al profilo insolite, ad esempio un aggiornamento del nome, numero di telefono o codice postale.
- Modifiche insolite alle credenziali, ad esempio, sono richiesti varie modifiche alla password.
- È stato aggiunto di recente un inoltro della posta di Outlook.
- È stata aggiunta una firma insolita, ad esempio una firma bancaria falsa o la fima per una ricetta medica.

Se un utente segnala qualsiasi dei sintomi precedenti, è necessario eseguire ulteriori analisi. [Microsoft 365 Defender](https://security.microsoft.com) e il portale di Azure offrono strumenti che consentono di analizzare le attività di un account utente che si sospetta possa essere compromesso.

- **Log di controllo unificati nel portale di Microsoft 365 Defender**: esaminare tutte le attività nell'account sospetto filtrando i risultati per l'intervallo di date che si estende da immediatamente prima delle attività sospette alla data attuale. Non filtrare le attività durante la ricerca.

- **Log di controllo dell'amministratore nell'interfaccia di amministrazione di Exchange**: in Exchange Online è possibile usare l'interfaccia di amministrazione di Exchange per cercare e visualizzare voci nel log di controllo dell'amministratore. Il log di controllo dell'amministratore registra operazioni specifiche, basate su cmdlet di PowerShell per Exchange Online, eseguite dagli amministratori e dagli utenti che dispongono di privilegi amministrativi. Le voci nel registro di controllo dell'amministratore forniscono informazioni sul cmdlet eseguito, sui parametri utilizzati, sull'utente che ha eseguito il cmdlet e sugli oggetti coinvolti.

- **Log di accesso di Azure AD e altri report sui rischi disponibili nel portale di Azure AD**: esaminare i valori nelle colonne seguenti:
  - Esaminare l'indirizzo IP
  - Posizioni di accesso
  - Orari di accesso
  - Esito dell’accesso

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a>Come proteggere e ripristinare la funzione di posta elettronica in un potenziale account e cassetta postale di Microsoft 365 compromessi.

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

Anche l’accesso all’account è stato riacquisito rapidamente, un utente malintenzionato potrebbe aver aggiunto voci “back-door” che gli permettono di riprendere il controllo dell'account.

È necessario eseguire la procedura seguente per accedere all'account il prima possibile per assicurarsi che l’autore dell’attacco non riprenda il controllo dell’account. Questa procedura consente di rimuovere le voci “back-door” che l’autore dell’attacco potrebbe aver aggiunto all’account. Dopo avere eseguito questi passaggi, è consigliabile eseguire una scansione con un programma antivirus per verificare che il computer non sia compromesso.

### <a name="step-1-reset-the-users-password"></a>Passaggio 1: Reimpostare la password dell’utente.

Seguire le procedure in [reimpostare la password per un utente ](../../admin/add-users/reset-passwords.md#reset-my-admin-password).

> [!IMPORTANT]
>
> - Non inviare la nuova password per l'utente desiderato tramite posta elettronica, poiché l’utente malintenzionato potrebbe ancora avere accesso alla cassetta postale.
>
> - Assicurarsi che la password sia complessa e che contenga lettere maiuscole e minuscole, almeno un numero e almeno un carattere speciale.
>
> - Non riutilizzare le ultime cinque password. Anche se il requisito di cronologia delle password consente di riutilizzare una password più recente, è necessario sceglierla in modo che un utente malintenzionato non possa indovinarla.
>
> - Se l'identità dell'utente locale è federata con Microsoft 365, è necessario cambiare la password locale e quindi informare l'amministratore della violazione.
>
> - Assicurati di aggiornare le password dell'app. Le password dell'app non vengono automaticamente revocate quando si reimposta la password di un account utente. L'utente deve eliminare le password dell'app esistenti e crearne nuove. Per istruzioni, vedere [creare ed eliminare password per le app dalla pagina Verifica di sicurezza aggiuntiva](/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).
>
> - È altamente consigliabile abilitare l'autenticazione a più fattori (MFA) per evitare violazioni, soprattutto per gli account con privilegi amministrativi. Per maggiori dettagli sull’autenticazione a più fattori, visitare [Configurare l’autenticazione a più fattori](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>Passaggio 2: Rimuovere indirizzi di inoltro della posta elettronica

1. Aprire l’interfaccia di amministrazione di Microsoft 365 in <https://admin.microsoft.com>

2. Passa a **Utenti** \> **Utenti attivi**. Trova l'account utente in questione e seleziona l'utente (riga) senza selezionare la casella di controllo.

3. Nel riquadro a comparsa dei dettagli visualizzato, seleziona la scheda **Posta**.

4. Se il valore nella sezione **Inoltro e-mail** è **Applicato**, fai clic su **Gestisci inoltro e-mail**. Nel riquadro a comparsa **Gestisci inoltro e-mail** visualizzato, deseleziona **Inoltra tutte le e-mail inviate a questa cassetta postale**, e fai clic su **Salva modifiche**.

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>Passaggio 3 disabilitare tutte le regole di posta in arrivo sospette

1. Aprire la cassetta postale dell’utente con Outlook sul web.

2. Fare clic sull'icona con l’ingranaggio e fare clic su **Posta**.

3. Fare clic su **Regole posta in arrivo e organizzazione** ed esaminare le regole.

4. Disattivare o eliminare le regole sospette.

### <a name="step-4-unblock-the-user-from-sending-mail"></a>Passaggio 4 Disattivare il blocco dell’invio di posta elettronica

Se la cassetta postale compromessa è stata usata illecitamente per inviare posta indesiderata, è probabile che la l'invio di posta elettronica sia stato bloccato.

Per sbloccare l’invio di posta elettronica da una cassetta postale, seguire le procedure descritte in [Rimozione di un utente dal portale Utenti con restrizioni dopo l'invio di posta elettronica indesiderata](removing-user-from-restricted-users-portal-after-spam.md).

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>Passaggio 5 facoltativo: Bloccare l’accesso all’account dell’utente

> [!IMPORTANT]
> È possibile bloccare l’accesso all’account compromesso fino a quando non si ritiene che sia sicuro abilitare di nuovo l'accesso.

1. Apri l'interfaccia di amministrazione di Microsoft 365 qui <https://admin.microsoft.com> e vai a **Utenti** \> **Utenti attivi**.

2. Trova e seleziona l'account utente, fai clic sull'![icona Altro](../../media/ITPro-EAC-MoreOptionsIcon.png) e seleziona **Modifica stato di accesso**.

3. Nel riquadro **Blocca accesso** visualizzato, seleziona **Impedisci a questo utente di accedere**, e fai clic su **Salva modifiche**.

4. Aprire l'interfaccia di amministrazione di Exchange qui <https://admin.exchange.microsoft.com> e passa a **Destinatari** \> **Cassette postali**.

5. Individua e seleziona l'utente. Nel riquadro a comparsa dei dettagli che si apre nella cassetta postale, seguire questi passaggi:
   - Nella sezione **App di posta elettronica**, bloccare tutte le impostazioni disponibili spostando il pulsante di alternanza su ![Disabilita](../../media/scc-toggle-on.png):
     - **Outlook sul web**
     - **Outlook desktop (MAPI)**
     - **Servizi Web Exchange**
     - **Dispositivo mobile (Exchange ActiveSync)**
     - **IMAP**
     - **POP3**

   Al termine, fai clic su **Salva**, quindi fai clic su **Chiudi**.

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>Passaggio 6 Facoltativo: Rimuovere l'account potenzialmente compromesso da tutti i gruppi di ruoli amministrativi

> [!NOTE]
> Dopo aver protetto l'account, è possibile ripristinare l'appartenenza ai gruppi di ruoli amministrativi.

1. Aprire l'interfaccia di amministrazione di Microsoft 365 qui <https://admin.microsoft.com> con l'account di amministratore globale e seguire questi passaggi:
   1. Passa a **Utenti** \> **Utenti attivi**.
   2. Trova e seleziona l'account utente, fai clic sull'![icona Altro](../../media/ITPro-EAC-MoreOptionsIcon.png) e seleziona **Gestisci ruoli**.
   3. Rimuovi gli eventuali ruoli da amministratore assegnati all'account. Al termine, fai clic su **salvare le modifiche**.

2. Aprire il portale di Microsoft 365 Defender qui <https://security.microsoft.com> e seguire questi passaggi:
   1. Passare a **Autorizzazioni e ruoli** \> **Posta elettronica e ruoli di collaborazione** \> **Ruoli**.
   2. Alla pagina **Autorizzazioni**, selezionare ogni gruppo di ruoli nell'elenco e cercare l'account utente nella sezione **Membri** del riquadro a comparsa dei dettagli che viene visualizzato. Se il gruppo di ruoli contiene l'account utente, eseguire le operazioni seguenti:
      1. Nella sezione **Membri** fare clic su **Modifica**.
      2. Nel riquadro a comparsa **Seleziona membri** visualizzato, fare clic su **Modifica**.
      3. Nel riquadro a comparsa **Scegli membri** visualizzato, fare clic su **Rimuovi**.
      4. Nel riquadro a comparsa visualizzato, selezionare l'account utente, quindi fare clic su **Rimuovi**.

         Al termine, fare clic su **Fine**, **Salva** e **Chiudi**.

3. Aprire l'interfaccia di amministrazione di Exchange qui <https://admin.exchange.microsoft.com> e seguire questi passaggi:
   1. Selezionare **Ruoli** \> **Ruoli di amministratore**.
   2. Alla pagina **Ruoli di amministratore**, selezionare manualmente ogni gruppo di ruolo, mentre nel riquadro dei dettagli selezionare la scheda **Assegnato** per verificare gli account utente. Se il gruppo di ruoli contiene l'account utente, eseguire le operazioni seguenti:
      1. Selezionare l'account utente.
      2. Fare clic su ![Icona Elimina](../../media/m365-cc-sc-delete-icon.png).

         Al termine, scegliere **Salva**.

### <a name="step-7-optional-additional-precautionary-steps"></a>Passaggio 7 facoltativo: Precauzioni di prevenzione aggiuntive

1. Assicurarsi di verificare i messaggi inviati. Potrebbe essere necessario informare gli utenti nell'elenco dei contatti che l'account è stato compromesso. Un utente malintenzionato potrebbe aver richiesto loro del denaro, fingendo (spoofing) che l’utente originale si trovasse bloccato in un paese/area geografica diversa e avesse necessità di denaro, oppure il malintenzionato potrebbe anche inviare dei virus per assumere il controllo dei loro computer. 

2. Qualsiasi altro servizio utilizzato con l'account di Exchange e il suo account di posta elettronica alternativo potrebbe essere compromesso. Prima di tutto, eseguire questi passaggi per l'abbonamento a Microsoft 365 poi seguire la stessa procedura per gli altri account.

3. Assicurarsi che le informazioni di contatto, ad esempio numeri di telefono e indirizzi, siano corrette.

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Proteggere Microsoft 365 come un professionista della sicurezza informatica

L'abbonamento a Microsoft 365 include un potente set di funzionalità di protezione che consente di proteggere i propri dati e quelli degli altri utenti.  Usare la [Roadmap della sicurezza di Microsoft 365: principali priorità per i primi 30 giorni, 90 giorni e oltre](security-roadmap.md) per implementare le procedure consigliate da Microsoft per proteggere il tenant di Microsoft 365.

- Attività da eseguire i primi 30 giorni. Queste hanno effetto immediato e sono a basso impatto per gli utenti.
- Attività da portare a termine in 90 giorni. Queste attività richiedono una quantità di tempo leggermente superiore per la pianificazione e l'implementazione, ma aumentano notevolmente il livello di sicurezza.
- Oltre 90 giorni. Questi miglioramenti si instaurano nei primi 90 giorni di lavoro effettuato.

## <a name="see-also"></a>Vedere anche

- [Rilevare e risolvere gli attacchi injection alle regole e ai moduli personalizzati di Outlook in Microsoft 365](detect-and-remediate-outlook-rules-forms-attack.md)
- [Internet Crime Complaint Center](https://www.ic3.gov/Home/Ransomware)
- [Securities and Exchange Commission (SEC) - Frode “Phishing”](https://www.sec.gov/investor/pubs/phishing.htm)
- Per segnalare messaggi di posta elettronica indesiderata direttamente a Microsoft e all'amministratore, [usare il componente aggiuntivo Segnala messaggio](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).
