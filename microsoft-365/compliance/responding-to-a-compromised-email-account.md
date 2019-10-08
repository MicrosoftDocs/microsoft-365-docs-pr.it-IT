---
title: Rispondere a un account di posta elettronica compromesso in Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.custom: TopSMBIssues
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Informazioni su come riconoscere e rispondere a un account di posta elettronica compromesso in Office 365
ms.openlocfilehash: 239e880bbdd1b2ef7cbbde7e42fb8392777563a5
ms.sourcegitcommit: 15173ab87325b7d79bab683702b35d77a355cd6b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2019
ms.locfileid: "37417575"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a>Rispondere a un account di posta elettronica compromesso in Office 365

**Riepilogo** Informazioni su come riconoscere e rispondere a un account di posta elettronica compromesso in Office 365.

## <a name="what-is-a-compromised-email-account-in-office-365"></a>Che cos'è un account di posta elettronica compromesso in Office 365?

L’accesso alle cassette postali, dati e altri servizi di Office 365 viene controllato tramite l’uso di credenziali, ad esempio un nome utente e la password o PIN. Quando un utente diverso da quello previsto sottrae queste credenziali, queste sono considerate compromesse. Con queste l'utente malintenzionato può accedere come utente originale ed effettuare operazioni illegali.
Usando le credenziali rubate, l'autore dell'attacco può accedere alla cassetta postale di Office 365 dell'utente, alle cartelle di SharePoint o ai file in OneDrive dell'utente. Un’operazione vista comunemente è l’invio da parte del pirata informatico di messaggi di posta elettronica a destinatari sia interni che esterni all'organizzazione dell'utente originale. Quando un utente malintenzionato invia dei dati tramite messaggi di posta elettronica a destinatari esterni, si chiama esfiltrazione di dati.

## <a name="symptoms-of-a-compromised-office-365-email-account"></a>Sintomi di un account di posta elettronica compromesso di Office 365

Gli utenti potrebbero notare e segnalare attività insolite nelle proprie cassette postali di Office 365. Ecco i sintomi più comuni:

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

- Log di controllo di Office 365 nel Centro sicurezza e conformità - Esaminare tutte le attività nell'account sospetto filtrando i risultati per l’intervallo di date che si estendono da immediatamente prima delle attività sospette alla data attuale. Non filtrare le attività durante la ricerca.
- Usare i log di accesso di Azure AD e i report di altri rischi disponibili nel portale di Azure Active Directory. Esaminare i valori in queste colonne:
    - Esaminare l'indirizzo IP
    - Posizioni di accesso
    - Orari di accesso
    - Esito dell’accesso

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a>Come proteggere e ripristinare la funzione di posta elettronica in un potenziale account e cassetta postale di Office 365 compromessi.

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

Anche l’accesso all’account è stato riacquisito rapidamente, un utente malintenzionato potrebbe aver aggiunto voci “back-door” che gli permettono di riprendere il controllo dell'account.

È necessario eseguire la procedura seguente per accedere all'account il prima possibile per assicurarsi che l’autore dell’attacco non riprenda il controllo dell’account. Questa procedura consente di rimuovere le voci “back-door” che l’autore dell’attacco potrebbe aver aggiunto all’account. Dopo avere eseguito questi passaggi, è consigliabile eseguire una scansione con un programma antivirus per verificare che il computer non sia compromesso.

### <a name="step-1-reset-the-users-password"></a>Passaggio 1: Reimpostare la password dell’utente.

> [!WARNING]
> Non inviare la nuova password per l'utente desiderato tramite posta elettronica, poiché l’utente malintenzionato potrebbe ancora avere accesso alla cassetta postale.

1. Seguire i passaggi descritti in Reimpostare la password di un altro utente in Office 365 Business per altri utenti in[Amministratori: reimpostare le password aziendali di Office 365](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)

**Note:**
- Assicurarsi che la password sia complessa e che contenga lettere maiuscole e minuscole, almeno un numero e almeno un carattere speciale. 
- Non riutilizzare le cinque password più recenti. Anche se il requisito di cronologia delle password consente di riutilizzare una password più recente, è necessario sceglierla in modo che un utente malintenzionato non possa indovinarla.
- Se l'identità dell'utente locale è federata con Office 365, è necessario cambiare la password locale e quindi informare l'amministratore della violazione.

> [!TIP]
> È altamente consigliabile abilitare l'autenticazione a più fattori (MFA) per evitare violazioni, soprattutto per gli account con privilegi amministrativi.  Ulteriori informazioni sono disponibili [qui](https://support.office.com/it-IT/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).

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
1. Per sbloccare l’invio di posta elettronica da una cassetta postale, seguire le procedure descritte in [Rimozione di un utente, dominio o indirizzo IP da un elenco di blocco dopo l'invio di posta elettronica indesiderata](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam).

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
5. Controllare manualmente i gruppi di ruoli per verificare se l’account potenzialmente compromesso sia un membro di uno di questi account.  Se è: a. Fare clic sul gruppo di ruoli e selezionare **Modifica gruppo di ruoli**.
    b. Fare clic su **Scegli membri** e **Modifica** per rimuovere l'utente dal gruppo di ruoli.
6. Aprire **l'interfaccia di amministrazione di Exchange**
7. Fare clic su **Autorizzazioni**.
8. Controllare manualmente i gruppi di ruoli per verificare se l’account potenzialmente compromesso sia un membro di uno di questi account. Se è: a. Fare clic sul gruppo di ruoli e selezionare **Modifica**.
    b. Fare clic sulla sezione**Membri** per rimuovere l'utente dal gruppo di ruoli.

### <a name="step-7-optional-additional-precautionary-steps"></a>Passaggio 7 facoltativo: Precauzioni di prevenzione aggiuntive

1. Assicurarsi di verificare i messaggi inviati. Potrebbe essere necessario informare gli utenti nell'elenco dei contatti che l'account è stato compromesso. Un utente malintenzionato potrebbe aver richiesto loro del denaro, fingendo (spoofing) che l’utente originale si trovasse bloccato in un paese/area geografica diversa e avesse necessità di denaro, oppure il malintenzionato potrebbe anche inviare dei virus per assumere il controllo dei loro computer. 
2. Qualsiasi altro servizio utilizzato con l'account di Exchange e il suo account di posta elettronica alternativo potrebbe essere compromesso. Prima di tutto, eseguire questi passaggi per l'abbonamento a Office 365 e seguire la stessa procedura per gli altri account.
3. Assicurarsi che le informazioni di contatto, ad esempio numeri di telefono e indirizzi, siano corrette.

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>Proteggere Office 365 come un professionista della sicurezza informatica

L'abbonamento a Office 365 include un potente set di funzionalità di protezione che consente di proteggere i propri dati e quelli degli altri utenti.  Usare il [Roadmap di protezione di Office 365: principali priorità per i primi 30 giorni, 90 giorni e oltre](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) per implementare le procedure consigliate da Microsoft per proteggere il tenant di Office 365.
- Attività da eseguire i primi 30 giorni.  Queste hanno effetto immediato e sono a basso impatto per gli utenti.
- Attività da completare in 90 giorni. Queste attività richiedono una quantità di tempo leggermente superiore per la pianificazione e l'implementazione, ma aumentano notevolmente il livello di sicurezza.
- Dopo 90 giorni. Questi miglioramenti si instaurano nei primi 90 giorni di lavoro effettuato.

## <a name="see-also"></a>Vedere anche:

- [Procedure consigliate per la sicurezza per Office 365](https://support.office.com/article/Security-best-practices-for-Office-365-9295e396-e53d-49b9-ae9b-0b5828cdedc3)
- [Rilevare e risolvere gli attacchi injection alle regole e ai moduli personalizzati di Outlook in Office 365](/security/office-365-security/detect-and-remediate-outlook-rules-forms-attack.md)
- [Internet Crime Complaint Center](http://www.ic3.gov/preventiontips.aspx)
- [Securities and Exchange Commission (SEC) - Frode “Phishing”](http://www.sec.gov/investor/pubs/phishing.htm)
- Per segnalare messaggi di posta elettronica indesiderata direttamente a Microsoft e all'amministratore, [usare il componente aggiuntivo Segnala messaggio](https://support.office.com/it-IT/article/Use-the-Report-Message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2).
