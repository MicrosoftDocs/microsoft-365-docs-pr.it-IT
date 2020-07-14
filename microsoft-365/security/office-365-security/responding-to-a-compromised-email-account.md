---
title: Rispondere a un account di posta elettronica compromesso
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Informazioni su come riconoscere e rispondere a un account di posta elettronica compromesso usando gli strumenti disponibili in Microsoft 365.
ms.openlocfilehash: f9d7b1dbcd9b54ca9b1bdca9e4a800be24286654
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094811"
---
# <a name="responding-to-a-compromised-email-account"></a>Rispondere a un account di posta elettronica compromesso

**Riepilogo** Informazioni su come riconoscere e rispondere a un account di posta elettronica compromesso in Microsoft 365.

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a>Che cos'è un account di posta elettronica compromesso in Microsoft 365?

L’accesso alle cassette postali, dati e altri servizi di Microsoft 365 viene controllato tramite l’uso di credenziali, ad esempio un nome utente e la password o il PIN. Quando un utente diverso da quello previsto sottrae queste credenziali, queste sono considerate compromesse. Con queste l'utente malintenzionato può accedere come utente originale ed effettuare operazioni illegali.
Usando le credenziali rubate, l'autore dell'attacco può accedere alla cassetta postale di Microsoft 365, alle cartelle di SharePoint o ai file in OneDrive dell'utente. Un’operazione vista comunemente è l’invio da parte del pirata informatico di messaggi di posta elettronica a destinatari sia interni che esterni all'organizzazione dell'utente originale. Quando un utente malintenzionato invia dei dati tramite messaggi di posta elettronica a destinatari esterni, si chiama esfiltrazione di dati.

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a>Sintomi di un account di posta elettronica Microsoft compromesso

Gli utenti potrebbero notare e segnalare attività insolite nelle proprie cassette postali di Microsoft 365. Ecco i sintomi più comuni:

- Attività sospette, ad esempio messaggi di posta elettronica mancanti o eliminati.

- Altri utenti potrebbero ricevere messaggi di posta elettronica dall'account compromesso senza che sia presente il messaggio di posta elettronica corrispondente nella cartella **Posta inviata** del mittente.

- La presenza di regole posta in arrivo che non sono state create dal proprietario o dall'amministratore. Queste regole possono inoltrare messaggi di posta elettronica a indirizzi sconosciuti o spostarli automaticamente nelle cartelle di**Note**, **Posta indesiderata**, o **Sottoscrizioni RSS**.

- Il nome visualizzato dell'utente può essere modificato nell'elenco indirizzi globale.

- Non è possibile inviare messaggi di posta elettronica dalla cassetta postale dell'utente.

- Le cartelle Posta inviata o Posta eliminata in Microsoft Outlook o Outlook sul web (precedentemente noto come Outlook Web App) contengono messaggi presenti comunemente in un account oggetto di un attacco, ad esempio "Mi sono bloccato a Milano, invia denaro."

- Modifiche al profilo insolite, ad esempio un aggiornamento del nome, numero di telefono o codice postale.

- Modifiche insolite alle credenziali, ad esempio, sono richiesti varie modifiche alla password.

- È stato aggiunto di recente un inoltro della posta di Outlook.

- È stata aggiunta una firma insolita, ad esempio una firma bancaria falsa o la fima per una ricetta medica.

Se un utente segnala qualsiasi dei sintomi precedenti, è necessario eseguire ulteriori analisi. Il Centro sicurezza e conformità di Microsoft 365 e il portale di Azure offfrono strumenti che consentono di analizzare le attività di un account utente che si sospetta potrebbe essere compromesso.

- **Log di controllo unificati nel Centro sicurezza e conformità**: esaminare tutte le attività nell'account sospetto filtrando i risultati per l'intervallo di date che si estendono da immediatamente prima delle attività sospette alla data attuale. Non filtrare le attività durante la ricerca.

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

> [!WARNING]
> Non inviare la nuova password per l'utente desiderato tramite posta elettronica, poiché l’utente malintenzionato potrebbe ancora avere accesso alla cassetta postale.

1. Seguire i passaggi descritti in Reimpostare la password di App Microsoft 365 for business per altri utenti in[Reimpostare le password per App Microsoft 365 for business](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)

**Note**:

- Assicurarsi che la password sia complessa e che contenga lettere maiuscole e minuscole, almeno un numero e almeno un carattere speciale.

- Non riutilizzare le cinque password più recenti. Anche se il requisito di cronologia delle password consente di riutilizzare una password più recente, è necessario sceglierla in modo che un utente malintenzionato non possa indovinarla.

- Se l'identità dell'utente locale è federata con Microsoft 365, è necessario cambiare la password locale e quindi informare l'amministratore della violazione.

> [!TIP]
> È altamente consigliabile abilitare l'autenticazione a più fattori (MFA) per evitare violazioni, soprattutto per gli account con privilegi amministrativi.  Per maggiori dettagli sull’autenticazione a più fattori, visitare [Configurare l’autenticazione a più fattori](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>Passaggio 2: Rimuovere indirizzi di inoltro della posta elettronica

1. Aprire l’**interfaccia di amministrazione di Microsoft 365 > Utenti attivi**.

2. Trovare l'account utente in questione ed espandere le ** impostazioni della posta**.

3. Su **Inoltro della posta elettronica**, fare clic su **Modifica**.

4. Rimuovere qualsiasi indirizzo di inoltro sospetto.

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

1. Passare all'interfaccia di amministrazione di Microsoft 365.

2. Nell'Interfaccia di amministrazione di Microsoft 365, selezionare **Utenti**.

3. Selezionare il dipendente da bloccare e scegliere **Modifica** accanto a **Stato accesso** nel riquadro degli utenti.

4. Nel riquadro **Stato accesso** scegliere **Accesso bloccato** e quindi **Salva**.

5. Nell'interfaccia di amministrazione nel riquadro di spostamento in basso a sinistra, espandere **Interfacce di amministrazione** e selezionare **Exchange**.

6. Nell'interfaccia di amministrazione di Exchange passare a **Destinatari > Cassette postali**.

7. Selezionare l'utente e nella relativa pagina delle proprietà, in **Dispositivi mobili**, selezionare **Disabilita Exchange ActiveSync**, **Disabilita OWA per i dispositivi** e rispondere **sì** per entrambi.

8. In **Connettività posta elettronica** fare clic su **Disabilita** e rispondere **sì**.

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>Passaggio 6 Facoltativo: Rimuovere l'account potenzialmente compromesso da tutti i gruppi di ruoli amministrativi

> [!NOTE]
> Dopo aver protetto l'account, è possibile ripristinare l'appartenenza ai gruppi di ruoli amministrativi.

1. Accedere all'interfaccia di amministrazione di Microsoft 365 con l'account di amministratore globale e aprire **Utenti attivi**.

2. Individuare i possibili account compromessi e controllare manualmente se sono presenti dei ruoli amministrativi assegnati all'account.

3. Aprire il **Centro sicurezza e conformità**.

4. Fare clic su **Autorizzazioni**.

5. Controllare manualmente i gruppi di ruoli per verificare se l’account potenzialmente compromesso sia un membro di uno di questi account.  Se è:

   a. Fare clic sul gruppo di ruoli e selezionare **Modifica gruppo di ruoli**.

   b. Fare clic su **Scegli membri** e **Modifica** per rimuovere l'utente dal gruppo di ruoli.

6. Aprire **l'interfaccia di amministrazione di Exchange**.

7. Fare clic su **Autorizzazioni**.

8. Controllare manualmente i gruppi di ruoli per verificare se l’account potenzialmente compromesso sia un membro di uno di questi account. Se è:

   a. Fare clic sul gruppo di ruoli e selezionare **Modifica**.

   b. Fare clic sulla sezione**Membri** per rimuovere l'utente dal gruppo di ruoli.

### <a name="step-7-optional-additional-precautionary-steps"></a>Passaggio 7 facoltativo: Precauzioni di prevenzione aggiuntive

1. Assicurarsi di verificare i messaggi inviati. Potrebbe essere necessario informare gli utenti nell'elenco dei contatti che l'account è stato compromesso. Un utente malintenzionato potrebbe aver richiesto loro del denaro, fingendo (spoofing) che l’utente originale si trovasse bloccato in un paese/area geografica diversa e avesse necessità di denaro, oppure il malintenzionato potrebbe anche inviare dei virus per assumere il controllo dei loro computer. 

2. Qualsiasi altro servizio utilizzato con l'account di Exchange e il suo account di posta elettronica alternativo potrebbe essere compromesso. Prima di tutto, eseguire questi passaggi per l'abbonamento a Microsoft 365 poi seguire la stessa procedura per gli altri account.

3. Assicurarsi che le informazioni di contatto, ad esempio numeri di telefono e indirizzi, siano corrette.

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Proteggere Microsoft 365 come un professionista della sicurezza informatica

L'abbonamento a Microsoft 365 include un potente set di funzionalità di protezione che consente di proteggere i propri dati e quelli degli altri utenti.  Usare la [Roadmap della sicurezza di Microsoft 365: principali priorità per i primi 30 giorni, 90 giorni e oltre](security-roadmap.md) per implementare le procedure consigliate da Microsoft per proteggere il tenant di Microsoft 365.

- Attività da eseguire i primi 30 giorni.  Queste hanno effetto immediato e sono a basso impatto per gli utenti.

- Attività da completare in 90 giorni. Queste attività richiedono una quantità di tempo leggermente superiore per la pianificazione e l'implementazione, ma aumentano notevolmente il livello di sicurezza.

- Dopo 90 giorni. Questi miglioramenti si instaurano nei primi 90 giorni di lavoro effettuato.

## <a name="see-also"></a>Vedere anche

- [Rilevare e risolvere gli attacchi injection alle regole e ai moduli personalizzati di Outlook in Microsoft 365](detect-and-remediate-outlook-rules-forms-attack.md)

- [Internet Crime Complaint Center](https://www.ic3.gov/preventiontips.aspx)

- [Securities and Exchange Commission (SEC) - Frode “Phishing”](https://www.sec.gov/investor/pubs/phishing.htm)

- Per segnalare messaggi di posta elettronica indesiderata direttamente a Microsoft e all'amministratore, [usare il componente aggiuntivo Segnala messaggio](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).
