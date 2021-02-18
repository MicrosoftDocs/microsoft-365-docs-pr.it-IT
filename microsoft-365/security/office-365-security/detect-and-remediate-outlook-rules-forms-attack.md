---
title: Rilevare e correggere gli attacchi di inserimento di regole e moduli personalizzati di Outlook.
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 04/23/2018
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: Informazioni su come riconoscere e correggere gli attacchi iniezioni di regole e moduli personalizzati di Outlook in Office 365
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e22cfa97ae59fdd094c161cdaeff899dc1dd6507
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286394"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>Rilevare e correggere gli attacchi iniezioni di regole e moduli personalizzati di Outlook

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Riepilogo** Informazioni su come riconoscere e correggere gli attacchi iniezioni di inserimenti di moduli personalizzati e regole di Outlook in Office 365.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>Che cos'è l'attacco di inserimento di regole e moduli personalizzati di Outlook?

Dopo che un utente malintenzionato ha violato un account nella tenancy e si è insediato, ci sarà il tentativo di stabilire un modo per rimanere o un modo per rientrare dopo che sono stati individuati e rimossi. Questa operazione viene definita creazione di un meccanismo di persistenza. A tale scopo, è possibile utilizzare le regole di Outlook o inserire moduli personalizzati in Outlook.
In entrambi i casi, la regola o il modulo viene sincronizzato dal servizio cloud fino al client desktop, in modo che un formato completo e la nuova installazione del software client non eliminino il meccanismo di inserimento. Questo perché quando il software client Outlook si riconnette alla cassetta postale nel cloud, scarica nuovamente le regole e i moduli dal cloud. Una volta che le regole e i moduli sono stati installati, l'utente malintenzionato le usa per eseguire codice remoto o personalizzato, in genere per installare malware nel computer locale. Il malware quindi ruba nuovamente le credenziali o esegue altre attività illecite.
La buona notizia è che se si mantiene i client patch alla versione più recente, non si è vulnerabili alla minaccia in quanto le impostazioni predefinite del client Outlook bloccano entrambi i meccanismi.

Gli attacchi in genere seguono questi modelli:

**L'exploit delle regole:**

1. L'autore dell'attacco ruba il nome utente e la password di uno degli utenti.

2. L'utente malintenzionato accede quindi alla cassetta postale di Exchange degli utenti. La cassetta postale può essere in Exchange online o in Exchange locale.

3. L'autore dell'attacco crea quindi una regola di inoltro nella cassetta postale che viene attivata quando la cassetta postale riceve un messaggio di posta elettronica che corrisponde ai criteri della regola. I criteri della regola e il contenuto del messaggio di posta elettronica trigger sono personalizzati l'uno per l'altro.

4. L'utente malintenzionato invia il messaggio di posta elettronica trigger all'utente che utilizza normalmente la propria cassetta postale.

5. Quando il messaggio di posta elettronica viene ricevuto, la regola viene attivata. L'azione della regola è in genere l'avvio di un'applicazione in un server remoto (WebDAV).

6. L'applicazione installa in genere malware, ad esempio [Powershell,](https://www.powershellempire.com/)localmente nel computer dell'utente.

7. Il malware consente all'utente malintenzionato di rubare nuovamente il nome utente e la password o altre credenziali dal computer locale ed eseguire altre attività dannose.

**L'exploit dei moduli:**

1. L'autore dell'attacco ruba il nome utente e la password di uno degli utenti.

2. L'utente malintenzionato accede quindi alla cassetta postale di Exchange degli utenti. La cassetta postale può essere in Exchange online o in Exchange locale.

3. L'autore dell'attacco crea quindi un modello di modulo di posta elettronica personalizzato e lo inserisce nella cassetta postale dell'utente. Il modulo personalizzato viene attivato quando la cassetta postale riceve un messaggio di posta elettronica che richiede che la cassetta postale carichi il modulo personalizzato. Il modulo personalizzato e il formato dei messaggi di posta elettronica sono personalizzati l'uno per l'altro.
4. L'utente malintenzionato invia il messaggio di posta elettronica trigger all'utente, che utilizza normalmente la propria cassetta postale.

5. Quando il messaggio di posta elettronica viene ricevuto, il modulo viene caricato. Il modulo avvia un'applicazione in un server Remoto (WebDAV).

6. L'applicazione installa in genere malware, ad esempio [Powershell,](https://www.powershellempire.com/)localmente nel computer dell'utente.

7. Il malware consente all'utente malintenzionato di rubare nuovamente il nome utente e la password o altre credenziali dal computer locale ed eseguire altre attività dannose.

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>Quale potrebbe essere l'aspetto di un attacco di inserimento di regole e moduli personalizzati come Office 365?

È improbabile che questi meccanismi di persistenza siano notati dagli utenti e in alcuni casi potrebbero anche essere invisibili. Questo articolo spiega come cercare uno dei sette segni (Indicatori di compromissione) elencati di seguito. Se si trova uno di questi elementi, è necessario eseguire la procedura di correzione.

- Indicatori della compromissione delle regole:

  - L'azione regola è avviare un'applicazione.

  - La regola fa riferimento a un FILE EXE, ZIP o URL.

  - Nel computer locale cercare i nuovi processi avviati dal PID di Outlook.

- Indicatori della compromissione dei moduli personalizzati:

  - Modulo personalizzato presente salvato come classe messaggio personalizzata.

  - La classe messaggio contiene codice eseguibile.

  - In genere archiviati nelle cartelle Libreria moduli personali o Posta in arrivo.

  - Il modulo è denominato IPM. Nota. [nome personalizzato].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Passaggi per individuare i segni di questo attacco e confermarlo

È possibile utilizzare uno di questi due metodi per confermare l'attacco:

- Esaminare manualmente le regole e i moduli per ogni cassetta postale utilizzando il client Outlook. Questo metodo è accurato, ma è possibile controllare solo l'utente della cassetta postale alla volta che può richiedere molto tempo se si dispone di molti utenti da controllare. Può anche causare una violazione del computer da cui si esegue il controllo.

- Utilizzare lo script [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell per eseguire automaticamente il dump di tutte le regole di inoltro della posta e i moduli personalizzati per tutti gli utenti della tenancy. Questo è il metodo più rapido e sicuro con il minor sovraccarico possibile.

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>Confermare l'attacco alle regole utilizzando il client Outlook

1. Aprire il client Outlook degli utenti come utente. L'utente potrebbe avere bisogno di assistenza per esaminare le regole nella propria cassetta postale.

2. Vedere [l'articolo sulla gestione dei messaggi di](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) posta elettronica utilizzando le regole per le procedure su come aprire l'interfaccia delle regole in Outlook.

3. Cercare le regole che l'utente non ha creato o eventuali regole impreviste o regole con nomi sospetti.

4. Cercare nella descrizione della regola le azioni delle regole che avviano e si ese verificano o fanno riferimento a un oggetto . EXE, . File ZIP o per avviare un URL.

5. Cercare eventuali nuovi processi che iniziano a utilizzare l'ID processo di Outlook. Fare riferimento [a Trovare l'ID processo.](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id)

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Procedura per confermare l'attacco ai moduli tramite il client Outlook

1. Aprire il client Outlook dell'utente come utente.

2. Seguire i passaggi descritti in [Mostra la scheda Sviluppo](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) per la versione di Outlook degli utenti.

3. Aprire la scheda sviluppatore ora visibile in Outlook e fare clic **su Progetta modulo.**

4. Selezionare Posta **in** arrivo **dall'elenco Cerca in.** Cercare eventuali moduli personalizzati. I moduli personalizzati sono abbastanza rari che, se si dispone di moduli personalizzati, vale la pena avere un aspetto più approfondito.

5. Analizzare eventuali moduli personalizzati, in particolare quelli contrassegnati come nascosti.

6. Aprire eventuali moduli personalizzati e nel **gruppo** Modulo fare clic su **Visualizza codice** per vedere cosa viene eseguito quando il modulo viene caricato.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Procedura per confermare l'attacco di regole e moduli tramite PowerShell

Il modo più semplice per verificare un attacco a regole o moduli personalizzati è eseguire lo script [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell. Questo script si connette a ogni cassetta postale nel tenant ed esegue il dump di tutte le regole e i moduli in due file CSV.

#### <a name="pre-requisites"></a>Prerequisiti

Per eseguire lo script, è necessario disporre di diritti di amministratore globale perché lo script si connette a tutte le cassette postali della tenancy per leggere le regole e i moduli.

1. Accedi al computer da cui eseguirai lo script con diritti di amministratore locale.

2. Scaricare o copiare lo script Get-AllTenantRulesAndForms.ps1 da GitHub in una cartella da cui verrà eseguito. Lo script creerà due file contrassegnati con data in questa cartella, MailboxFormsExport-yyyy-mm-dd.csv e MailboxRulesExport-yyyy-mm-dd.csv.

3. Aprire un'istanza di PowerShell come amministratore e aprire la cartella in cui è stato salvato lo script.

4. Eseguire questa riga di comando di PowerShell come indicato di `.\Get-AllTenantRulesAndForms.ps1` seguito.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>Interpretazione dell'output

- **MailboxRulesExport-*aaaa-mm-gg*.csv**: esaminare le regole (una per riga) per le condizioni di azione che includono applicazioni o eseguibili:

  - **ActionType (colonna A):** se viene visualizzato il valore "ID_ACTION_CUSTOM", è probabile che la regola sia dannosa.

  - **IsPotentiallyMalicious (colonna D):** se questo valore è "TRUE", è probabile che la regola sia dannosa.

  - **ActionCommand (colonna G):** se viene elencata un'applicazione o un file con estensione exe, zip o una voce che fa riferimento a un URL, che non dovrebbe essere presente, è probabile che la regola sia dannosa.

- **MailboxFormsExport-*aaaa-mm-gg*.csv:** in generale, l'utilizzo di moduli personalizzati è molto raro. Se nella cartella di lavoro è presente una cartella di lavoro, aprire la cassetta postale dell'utente ed esaminare il modulo stesso. Se l'organizzazione non l'ha inserita intenzionalmente, è probabile che sia dannosa.

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Come arrestare e correggere l'attacco alle regole e ai moduli di Outlook

Se si trovano prove di uno di questi attacchi, la correzione è semplice, basta eliminare la regola o il modulo dalla cassetta postale. A tale scopo, è possibile utilizzare il client Outlook o PowerShell remoto per rimuovere le regole.

### <a name="using-outlook"></a>Utilizzo di Outlook

1. Identificare tutti i dispositivi utilizzati dall'utente con Outlook. Dovranno essere tutti puliti dal potenziale malware. Non consentire all'utente di accedere e usare la posta elettronica finché non vengono puliti tutti i dispositivi.

2. Seguire i passaggi descritti in [Eliminare una regola](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) per ogni dispositivo.

3. Se non si è sicuri della presenza di altro malware, è possibile formattare e installare di nuovo tutto il software nel dispositivo. Per i dispositivi mobili puoi seguire i passaggi del produttore per ripristinare l'immagine di fabbrica del dispositivo.

4. Installare le versioni più aggiornate di Outlook. Tenere presente che la versione corrente di Outlook blocca entrambi i tipi di attacco per impostazione predefinita.

5. Dopo aver rimosso tutte le copie offline della cassetta postale, reimpostare la password dell'utente (utilizzarne una di alta qualità) e seguire i passaggi descritti [in](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) Configurare l'autenticazione a più fattori per gli utenti se l'autenticazione a più fattori non è già stata abilitata. Ciò garantisce che le credenziali dell'utente non siano esposte tramite altri mezzi (ad esempio phishing o re-uso della password).

### <a name="using-powershell"></a>Utilizzo di PowerShell

Esistono due cmdlet di PowerShell remoti che è possibile utilizzare per rimuovere o disabilitare le regole pericolose. Seguire i passaggi.

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Passaggi per le cassette postali presenti in un server Exchange

1. Connettersi al server Exchange utilizzando Remote PowerShell. Seguire i passaggi descritti in [Connettersi ai server Exchange tramite PowerShell remoto.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)

2. Se si desidera rimuovere completamente una singola regola, più regole o tutte le regole da una cassetta postale, utilizzare il cmdlet [Remove-InboxRule.](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule)

3. Se si desidera mantenere la regola e il relativo contenuto per ulteriori indagini, utilizzare il cmdlet [Disable-InboxRule.](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule)

#### <a name="steps-for-mailboxes-in-exchange-online"></a>Passaggi per le cassette postali in Exchange Online

1. Seguire i passaggi descritti in [Connettersi a Exchange Online tramite PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. Se si desidera rimuovere completamente una singola regola, più regole o tutte le regole da una cassetta postale, utilizzare il cmdlet [Remove-Inbox Rule.](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule)

3. Se si desidera mantenere la regola e il relativo contenuto per ulteriori indagini, utilizzare il cmdlet [Disable-InboxRule.](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule)

## <a name="how-to-minimize-future-attacks"></a>Come ridurre al minimo gli attacchi futuri

### <a name="first-protect-your-accounts"></a>Prima di tutto: proteggere gli account

Gli exploit regole e moduli vengono usati da un utente malintenzionato solo dopo aver rubato o violato uno degli account dell'utente. Pertanto, il primo passaggio per impedire l'uso di questi exploit nell'organizzazione consiste nel proteggere in modo aggressivo gli account utente. Alcuni dei modi più comuni in cui vengono violati gli account sono gli attacchi di phishing [o di irrorazione delle password.](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/)

Il modo migliore per proteggere gli account utente, in particolare gli account amministratore, è configurare l'autenticazione a più [fattori per gli utenti.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) È inoltre consigliabile:

- Monitorare la modalità di accesso e utilizzo [degli account utente.](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports) Non è possibile impedire la violazione iniziale, ma si ridurrà la durata e l'impatto della violazione rilevandola prima. È possibile usare questi criteri [di Office 365 Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) per monitorare gli account e avvisare in caso di attività insolite:

  - **Più tentativi** di accesso non riusciti: questo criterio consente di profilire l'ambiente e di attivare avvisi quando gli utenti eseguono più attività di accesso non riuscite in una singola sessione rispetto alla linea di base appresa, che potrebbe indicare un tentativo di violazione.

  - **Viaggi impossibili:** questo criterio consente di profilire l'ambiente e di attivare avvisi quando le attività vengono rilevate dallo stesso utente in posizioni diverse in un periodo di tempo inferiore al tempo di viaggio previsto tra le due posizioni. Ciò potrebbe indicare che un utente diverso usa le stesse credenziali. Il rilevamento di questo comportamento anomalo richiede un periodo di apprendimento iniziale di sette giorni durante il quale apprende il modello di attività di un nuovo utente.

  - **Attività impersonata** insolita (da parte dell'utente): questo criterio consente di profilire l'ambiente e di attivare avvisi quando gli utenti eseguono più attività rappresentate in una singola sessione rispetto alla previsione appresa, che potrebbe indicare un tentativo di violazione.

- Sfruttare uno strumento come [Office 365 Secure Score per](https://securescore.office.com/) gestire le configurazioni e i comportamenti di sicurezza dell'account.

### <a name="second-keep-your-outlook-clients-current"></a>Secondo: Mantenere i client Outlook sempre attivi

Le versioni completamente aggiornate e con patch di Outlook 2013 e 2016 disabilitano l'azione regola/modulo "Avvia applicazione" per impostazione predefinita. In questo modo, anche se un utente malintenzionato viola l'account, le azioni della regola e del modulo verranno bloccate. È possibile installare gli aggiornamenti e le patch di sicurezza più recenti seguendo la procedura descritta in [Installare gli aggiornamenti di Office.](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)

Ecco le versioni delle patch per i client Outlook 2013 e 2016:

- **Outlook 2016**: 16.0.4534.1001 o versione successiva.

- **Outlook 2013**: 15.0.4937.1000 o versione successiva.

Per ulteriori informazioni sulle singole patch di sicurezza, vedere:

- [Patch di sicurezza di Outlook 2016](https://support.microsoft.com/help/3191883)

- [Patch di sicurezza di Outlook 2013](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>Terzo: monitorare i client Outlook

Tieni presente che anche con le patch e gli aggiornamenti installati, un utente malintenzionato può modificare la configurazione del computer locale per abilitare nuovamente il comportamento "Avvia applicazione". È possibile utilizzare [Gestione avanzata Criteri di gruppo](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) per monitorare e applicare i criteri del computer locale ai client.

Puoi vedere se "Avvia applicazione" è stato ri-abilitato tramite una sostituzione nel Registro di sistema usando le informazioni in Come visualizzare il Registro di sistema usando le versioni a [64 bit di Windows.](https://support.microsoft.com/help/305097) Controllare queste sottochiavi:

- **Outlook 2016:**`HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013:**`HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

Cercare la chiave EnableUnsafeClientMailRules. Se è presente ed è impostato su 1, la patch di sicurezza di Outlook è stata ignorata e il computer è vulnerabile all'attacco modulo/regole. Se il valore è 0, l'azione "Avvia applicazione" viene disabilitata. Se è installata la versione aggiornata e con patch di Outlook e questa chiave del Registro di sistema non è presente, un sistema non è vulnerabile a questi attacchi.

I clienti con installazioni di Exchange locali devono prendere in considerazione la possibilità di bloccare le versioni precedenti di Outlook che non dispongono di patch disponibili. Per informazioni dettagliate su questo processo, vedere l'articolo [Configure Outlook client blocking.](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Proteggere Microsoft 365 come un professionista della sicurezza informatica

L'abbonamento a Microsoft 365 include un potente set di funzionalità di protezione che consente di proteggere i propri dati e quelli degli altri utenti. Usare la [Roadmap della sicurezza di Microsoft 365: principali priorità per i primi 30 giorni, 90 giorni e oltre](security-roadmap.md) per implementare le procedure consigliate da Microsoft per proteggere il tenant di Microsoft 365.

- Attività da eseguire i primi 30 giorni. Queste hanno effetto immediato e sono a basso impatto per gli utenti.

- Attività da completare in 90 giorni. Queste attività richiedono una quantità di tempo leggermente superiore per la pianificazione e l'implementazione, ma aumentano notevolmente il livello di sicurezza.

- Dopo 90 giorni. Questi miglioramenti si instaurano nei primi 90 giorni di lavoro effettuato.

## <a name="see-also"></a>Vedere anche:

- [Malicious Outlook Rules](https://silentbreaksecurity.com/malicious-outlook-rules/) by SilentBreak Security Post about Rules Vector fornisce una revisione dettagliata del modo in cui le regole di Outlook.

- [MAPI su HTTP e Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) nel blog Sensepost su Mailrule Pwnage illustra uno strumento denominato Ruler che consente di sfruttare le cassette postali tramite le regole di Outlook.

- [Moduli e shell di Outlook nel](https://sensepost.com/blog/2017/outlook-forms-and-shells/) blog Sensepost su Forms Threat Vector.

- [Codebase righello](https://github.com/sensepost/ruler)

- [Indicatori di compromissione dei righelli](https://github.com/sensepost/notruler/blob/master/iocs.md)
