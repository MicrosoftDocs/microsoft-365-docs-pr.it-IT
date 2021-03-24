---
title: Rilevare e correggere le regole di Outlook e gli attacchi di inserimento di moduli personalizzati.
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
description: Informazioni su come riconoscere e correggere gli attacchi iniezioni di moduli personalizzati e regole di Outlook in Office 365
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0846051b65b34ec26358f87bb4ca49302573e6e7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064533"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>Rilevare e correggere le regole di Outlook e gli attacchi iniezioni di moduli personalizzati

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Riepilogo** Informazioni su come riconoscere e correggere le regole di Outlook e gli attacchi iniezioni di moduli personalizzati in Office 365.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>Che cos'è l'attacco di inserimento di regole e moduli personalizzati di Outlook?

Dopo che un utente malintenzionato ottiene l'accesso all'organizzazione, tenterà di stabilire un punto di appoggio per rimanere o rientrare dopo essere stato individuato. Questa attività è denominata *definizione di un meccanismo di persistenza.* Un utente malintenzionato può utilizzare Outlook in due modi per stabilire un meccanismo di persistenza:

- Sfruttando le regole di Outlook.
- Iniettando moduli personalizzati in Outlook.

La reinstallazione di Outlook o anche l'installazione di un nuovo computer da parte della persona interessata non sarà utile. Quando la nuova installazione di Outlook si connette alla cassetta postale, tutte le regole e i moduli vengono sincronizzati dal cloud. Le regole o i moduli sono in genere progettati per eseguire codice remoto e installare malware nel computer locale. Il malware ruba le credenziali o esegue altre attività illecite.

La buona notizia è che se si mantiene i client outlook patch alla versione più recente, non si è vulnerabili alla minaccia in quanto le impostazioni predefinite correnti del client outlook bloccano entrambi i meccanismi.

Gli attacchi in genere seguono questi modelli:

**L'exploit delle regole**:

1. L'autore dell'attacco ruba le credenziali di un utente.

2. L'autore dell'attacco accede alla cassetta postale di Exchange dell'utente (Exchange Online o Exchange locale).

3. L'autore dell'attacco crea una regola di posta in arrivo di inoltro nella cassetta postale. La regola di inoltro viene attivata quando la cassetta postale riceve un messaggio specifico dall'autore dell'attacco che soddisfa le condizioni della regola. Le condizioni della regola e il formato del messaggio sono personalizzati l'uno per l'altro.

4. L'utente malintenzionato invia il messaggio di posta elettronica di attivazione alla cassetta postale compromessa, che viene comunque utilizzata normalmente dall'utente ignara.

5. Quando la cassetta postale riceve un messaggio che soddisfa le condizioni della regola, viene applicata l'azione della regola. In genere, l'azione della regola è avviare un'applicazione in un server remoto (WebDAV).

6. In genere, l'applicazione installa malware nel computer dell'utente (ad esempio, [PowerShell Imperial](https://www.powershellempire.com/)).

7. Il malware consente all'utente malintenzionato di rubare (o rubare di nuovo) il nome utente e la password o altre credenziali dal computer locale ed eseguire altre attività dannose.

**L'exploit dei moduli**:

1. L'autore dell'attacco ruba le credenziali di un utente.

2. L'autore dell'attacco accede alla cassetta postale di Exchange dell'utente (Exchange Online o Exchange locale).

3. L'autore dell'attacco inserisce un modello di modulo di posta elettronica personalizzato nella cassetta postale dell'utente. Il modulo personalizzato viene attivato quando la cassetta postale riceve un messaggio specifico dall'autore dell'attacco che richiede alla cassetta postale di caricare il modulo personalizzato. Il modulo personalizzato e il formato del messaggio sono personalizzati l'uno per l'altro.

4. L'utente malintenzionato invia il messaggio di posta elettronica di attivazione alla cassetta postale compromessa, che viene comunque utilizzata normalmente dall'utente ignara.

5. Quando la cassetta postale riceve il messaggio, la cassetta postale carica il modulo necessario. Il modulo avvia un'applicazione in un server remoto (WebDAV).

6. In genere, l'applicazione installa malware nel computer dell'utente (ad esempio, [PowerShell Imperial](https://www.powershellempire.com/)).

7. Il malware consente all'utente malintenzionato di rubare (o rubare di nuovo) il nome utente e la password o altre credenziali dal computer locale ed eseguire altre attività dannose.

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>Che aspetto potrebbe avere un attacco di inserimento di regole e moduli personalizzati come Office 365?

È improbabile che questi meccanismi di persistenza siano notati dagli utenti e in alcuni casi potrebbero anche essere invisibili. In questo articolo viene illustrato come cercare uno dei sette segni (Indicatori di compromissione) elencati di seguito. Se si trova uno di questi elementi, è necessario eseguire la procedura di correzione.

- **Indicatori della compromissione delle regole**:
  - Regola L'azione consente di avviare un'applicazione.
  - La regola fa riferimento a un FILE EXE, ZIP o URL.
  - Nel computer locale cercare i nuovi processi avviati dal PID di Outlook.

- **Indicatori della compromissione dei moduli personalizzati:**
  - Moduli personalizzati presenti salvati come classe messaggio personalizzata.
  - La classe messaggio contiene codice eseguibile.
  - In genere, i moduli dannosi vengono archiviati nelle cartelle Libreria moduli personali o Posta in arrivo.
  - Il modulo è denominato IPM. Nota. [nome personalizzato].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Passaggi per trovare i segni di questo attacco e confermarlo

È possibile utilizzare uno dei metodi seguenti per confermare l'attacco:

- Esaminare manualmente le regole e i moduli per ogni cassetta postale utilizzando il client Outlook. Questo metodo è accurato, ma è possibile controllare solo una cassetta postale alla volta. Questo metodo può richiedere molto tempo se hai molti utenti da controllare e potrebbe anche infettare il computer in uso.

- Usa lo script [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell per scaricare automaticamente tutte le regole di inoltro della posta e i moduli personalizzati per tutti gli utenti della tenancy. Questo è il metodo più rapido e sicuro con il minor sovraccarico.

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>Confermare l'attacco alle regole utilizzando il client Outlook

1. Aprire il client Outlook degli utenti come utente. L'utente potrebbe avere bisogno del supporto per esaminare le regole della propria cassetta postale.

2. Per le [procedure su](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) come aprire l'interfaccia delle regole in Outlook, vedere Gestire i messaggi di posta elettronica utilizzando le regole.

3. Cercare le regole che l'utente non ha creato o eventuali regole impreviste o regole con nomi sospetti.

4. Cercare nella descrizione della regola le azioni delle regole avviate e applicazioni o che fanno riferimento a un oggetto . EXE, . ZIP o per avviare un URL.

5. Cercare eventuali nuovi processi che iniziano a utilizzare l'ID processo di Outlook. Fare riferimento [a Trovare l'ID processo](/windows-hardware/drivers/debugger/finding-the-process-id).

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Passaggi per confermare l'attacco dei moduli tramite il client Outlook

1. Aprire il client Outlook dell'utente come utente.

2. Seguire i passaggi descritti in [Show the Developer tab](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) for the user's version of Outlook.

3. Aprire la scheda sviluppatore ora visibile in Outlook e fare clic **su Progetta un modulo.**

4. Selezionare Posta **in** arrivo **nell'elenco Cerca in.** Cercare eventuali moduli personalizzati. I moduli personalizzati sono abbastanza rari che, se si dispone di moduli personalizzati, vale la pena di avere un'occhiata più approfondita.

5. Analizzare eventuali moduli personalizzati, in particolare quelli contrassegnati come nascosti.

6. Aprire eventuali moduli personalizzati e nel gruppo **Modulo** fare clic **su Visualizza codice** per vedere cosa viene eseguito quando il modulo viene caricato.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Passaggi per confermare l'attacco di regole e moduli tramite PowerShell

Il modo più semplice per verificare un attacco a regole o moduli personalizzati è eseguire lo script [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell. Questo script si connette a ogni cassetta postale del tenant e scarica tutte le regole e i moduli in due file CSV.

#### <a name="pre-requisites"></a>Prerequisiti

Sarà necessario disporre dei diritti di amministratore globale per eseguire lo script perché lo script si connette a ogni cassetta postale nella tenancy per leggere le regole e i moduli.

1. Accedi al computer da cui eseguirai lo script con diritti di amministratore locale.

2. Scaricare o copiare Get-AllTenantRulesAndForms.ps1 script da GitHub in una cartella da cui verrà eseguito. Lo script creerà due file contrassegnati con data in questa cartella, MailboxFormsExport-yyyy-mm-dd.csv e MailboxRulesExport-yyyy-mm-dd.csv.

3. Aprire un'istanza di PowerShell come amministratore e aprire la cartella in cui è stato salvato lo script.

4. Eseguire questa riga di comando di PowerShell come `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>Interpretazione dell'output

- **MailboxRulesExport-*aaaa-mm-dd*.csv**: esaminare le regole (una per riga) per le condizioni di azione che includono applicazioni o eseguibili:

  - **ActionType (colonna A):** se viene visualizzato il valore "ID_ACTION_CUSTOM", è probabile che la regola sia dannosa.

  - **IsPotentiallyMalicious (colonna D):** se questo valore è "TRUE", è probabile che la regola sia dannosa.

  - **ActionCommand (colonna G):** se questa colonna elenca un'applicazione o un file con estensioni exe o zip o una voce sconosciuta che fa riferimento a un URL, è probabile che la regola sia dannosa.

- **MailboxFormsExport-*yyyy-mm-dd*.csv**: in generale, l'utilizzo di moduli personalizzati è raro. Se nella cartella di lavoro è presente una cartella di lavoro, aprire la cassetta postale dell'utente ed esaminare il modulo stesso. Se l'organizzazione non l'ha inserita intenzionalmente, è probabile che sia dannosa.

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Come arrestare e correggere l'attacco di regole e moduli di Outlook

Se si trova una prova di uno di questi attacchi, la correzione è semplice, basta eliminare la regola o il modulo dalla cassetta postale. A tale scopo, è possibile utilizzare il client Outlook o PowerShell remoto per rimuovere le regole.

### <a name="using-outlook"></a>Utilizzo di Outlook

1. Identificare tutti i dispositivi utilizzati dall'utente con Outlook. Tutti dovranno essere puliti da potenziali malware. Non consentire all'utente di accedere e usare la posta elettronica finché non vengono puliti tutti i dispositivi.

2. Segui i passaggi descritti in [Eliminare una regola](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) per ogni dispositivo.

3. Se non sei sicuro della presenza di altro malware, puoi formattare e reinstallare tutto il software nel dispositivo. Per i dispositivi mobili, puoi seguire la procedura dei produttori per reimpostare il dispositivo sull'immagine di fabbrica.

4. Installare le versioni più aggiornate di Outlook. Tenere presente che la versione corrente di Outlook blocca entrambi i tipi di attacco per impostazione predefinita.

5. Dopo aver rimosso tutte le copie offline della cassetta postale, reimpostare la password dell'utente (usarne una di alta qualità) e seguire i passaggi descritti in [Configurare](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) l'autenticazione a più fattori per gli utenti se la MFA non è già stata abilitata. In questo modo si garantisce che le credenziali dell'utente non siano esposte con altri mezzi (ad esempio phishing o ri-uso della password).

### <a name="using-powershell"></a>Utilizzo di PowerShell

Esistono due cmdlet di PowerShell remoti che è possibile utilizzare per rimuovere o disabilitare le regole pericolose. Basta seguire i passaggi.

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Passaggi per le cassette postali presenti in un server Exchange

1. Connettersi al server Exchange tramite PowerShell remoto. Seguire i passaggi descritti in [Connect to Exchange servers using remote PowerShell](/powershell/exchange/connect-to-exchange-servers-using-remote-powershell).

2. Se si desidera rimuovere completamente una singola regola, più regole o tutte le regole da una cassetta postale, utilizzare il cmdlet [Remove-InboxRule.](/powershell/module/exchange/Remove-InboxRule)

3. Se si desidera conservare la regola e il relativo contenuto per ulteriori indagini, utilizzare il cmdlet [Disable-InboxRule.](/powershell/module/exchange/disable-inboxrule)

#### <a name="steps-for-mailboxes-in-exchange-online"></a>Passaggi per le cassette postali in Exchange Online

1. Seguire i passaggi descritti in [Connect to Exchange Online using PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Se si desidera rimuovere completamente una singola regola, più regole o tutte le regole da una cassetta postale, utilizzare il cmdlet [Remove-Inbox Rule.](/powershell/module/exchange/Remove-InboxRule)

3. Se si desidera conservare la regola e il relativo contenuto per ulteriori indagini, utilizzare il cmdlet [Disable-InboxRule.](/powershell/module/exchange/disable-inboxrule)

## <a name="how-to-minimize-future-attacks"></a>Come ridurre al minimo gli attacchi futuri

### <a name="first-protect-your-accounts"></a>Primo: proteggere gli account

Gli exploit Regole e moduli vengono utilizzati da un utente malintenzionato solo dopo aver rubato o violato uno degli account dell'utente. Pertanto, il primo passaggio per impedire l'utilizzo di questi exploit contro l'organizzazione consiste nel proteggere in modo aggressivo gli account utente. Alcuni dei modi più comuni in cui vengono violati gli account sono gli attacchi di phishing o [di spray con password.](https://www.microsoft.com/security/blog/2020/04/23/protecting-organization-password-spray-attacks/)

Il modo migliore per proteggere gli account utente e in particolare gli account amministratore è configurare l'autenticazione a più fattori [per gli utenti.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) È inoltre consigliabile:

- Monitorare la modalità di accesso e utilizzo [degli account utente.](/azure/active-directory/active-directory-view-access-usage-reports) Non puoi impedire la violazione iniziale, ma ridurrai la durata e l'impatto della violazione rilevandola prima. È possibile usare questi criteri [di Office 365 Cloud App Security](/cloud-app-security/what-is-cloud-app-security) per monitorare gli account e avvisare le attività insolite:

  - **Più tentativi** di accesso non riusciti: questo criterio profili l'ambiente e attiva avvisi quando gli utenti eseguono più attività di accesso non riuscite in una singola sessione rispetto alla linea di base appresa, che potrebbe indicare un tentativo di violazione.

  - **Viaggi impossibili:** questo criterio consente di profilire l'ambiente e di attivare avvisi quando vengono rilevate attività dallo stesso utente in posizioni diverse in un periodo di tempo inferiore al tempo di viaggio previsto tra le due posizioni. Ciò potrebbe indicare che un utente diverso usa le stesse credenziali. Il rilevamento di questo comportamento anomalo richiede un periodo di apprendimento iniziale di sette giorni durante il quale apprende il modello di attività di un nuovo utente.

  - Attività impersonata insolita **(dall'utente):** questo criterio profili l'ambiente e attiva avvisi quando gli utenti eseguono più attività rappresentate in una singola sessione rispetto alla linea di base appresa, che potrebbe indicare un tentativo di violazione.

- Usare uno strumento come [Punteggio sicuro di Office 365](https://securescore.office.com/) per gestire le configurazioni e i comportamenti di sicurezza degli account.

### <a name="second-keep-your-outlook-clients-current"></a>Secondo: Mantenere i client Outlook correnti

Le versioni completamente aggiornate e con patch di Outlook 2013 e 2016 disabilitano l'azione regola/modulo "Avvia applicazione" per impostazione predefinita. In questo modo, anche se un utente malintenzionato viola l'account, le azioni della regola e del modulo verranno bloccate. È possibile installare gli aggiornamenti e le patch di sicurezza più recenti seguendo la procedura descritta in [Installare gli aggiornamenti di Office.](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)

Ecco le versioni della patch per i client Outlook 2013 e 2016:

- **Outlook 2016**: 16.0.4534.1001 o versione successiva.

- **Outlook 2013**: 15.0.4937.1000 o versione successiva.

Per ulteriori informazioni sulle singole patch di sicurezza, vedere:

- [Patch di sicurezza per Outlook 2016](https://support.microsoft.com/help/3191883)

- [Patch di sicurezza per Outlook 2013](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>Terzo: monitorare i client outlook

Si noti che, anche con le patch e gli aggiornamenti installati, è possibile che un utente malintenzionato modii la configurazione del computer locale per abilitare nuovamente il comportamento "Avvia applicazione". È possibile utilizzare [Gestione avanzata Criteri di gruppo](/microsoft-desktop-optimization-pack/agpm/) per monitorare e applicare i criteri del computer locale ai client.

Puoi vedere se "Avvia applicazione" è stato ri-abilitato tramite una sostituzione nel Registro di sistema usando le informazioni in [How to view the system registry by using 64-bit versions of Windows](https://support.microsoft.com/help/305097). Controllare queste sottochiavi:

- **Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

Cercare la chiave EnableUnsafeClientMailRules. Se è presente ed è impostato su 1, la patch di sicurezza di Outlook è stata ignorata e il computer è vulnerabile all'attacco Modulo/Regole. Se il valore è 0, l'azione "Avvia applicazione" è disabilitata. Se è installata la versione aggiornata e con patch di Outlook e questa chiave del Registro di sistema non è presente, un sistema non è vulnerabile a questi attacchi.

I clienti con installazioni di Exchange locali devono prendere in considerazione la possibilità di bloccare le versioni precedenti di Outlook in cui non sono disponibili patch. Per informazioni dettagliate su questo processo, vedere l'articolo [Configure Outlook client blocking](/exchange/configure-outlook-client-blocking-exchange-2013-help).

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Proteggere Microsoft 365 come un professionista della sicurezza informatica

L'abbonamento a Microsoft 365 include un potente set di funzionalità di protezione che consente di proteggere i propri dati e quelli degli altri utenti. Usare la [Roadmap della sicurezza di Microsoft 365: principali priorità per i primi 30 giorni, 90 giorni e oltre](security-roadmap.md) per implementare le procedure consigliate da Microsoft per proteggere il tenant di Microsoft 365.

- Attività da eseguire i primi 30 giorni. Questi hanno un effetto immediato e hanno un impatto basso per gli utenti.

- Attività da completare in 90 giorni. Queste attività richiedono una quantità di tempo leggermente superiore per la pianificazione e l'implementazione, ma aumentano notevolmente il livello di sicurezza.

- Dopo 90 giorni. Questi miglioramenti si instaurano nei primi 90 giorni di lavoro effettuato.

## <a name="see-also"></a>Vedere anche:

- [Malicious Outlook Rules](https://silentbreaksecurity.com/malicious-outlook-rules/) by SilentBreak Security Post about Rules Vector fornisce una revisione dettagliata del modo in cui le regole di Outlook.

- [MAPI su HTTP e Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) nel blog Sensepost su Mailrule Pwnage illustra uno strumento denominato Ruler che consente di sfruttare le cassette postali tramite le regole di Outlook.

- [Moduli e shell di Outlook nel](https://sensepost.com/blog/2017/outlook-forms-and-shells/) blog sensepost su Forms Threat Vector.

- [Codebase righello](https://github.com/sensepost/ruler)

- [Indicatori di compromissione dei righelli](https://github.com/sensepost/notruler/blob/master/iocs.md)