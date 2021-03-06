---
title: Usare le regole di riduzione della superficie di attacco per prevenire l'infezione da malware
description: Le regole di riduzione della superficie di attacco possono impedire agli exploit di usare app e script per infettare i dispositivi con malware.
keywords: Regole di riduzione della superficie di attacco, asr, fianchi, sistema di prevenzione delle intrusioni host, regole di protezione, anti-exploit, antiexploit, exploit, prevenzione delle infezioni, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde, sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ed6dc9956c3e78f8ed39dca9cd6bf0421dd28456
ms.sourcegitcommit: 8c6a5db0dab99a82a69dd8a0a7c56af1cb825931
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2021
ms.locfileid: "53276990"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a>Usare le regole di riduzione della superficie di attacco per prevenire l'infezione da malware

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="why-attack-surface-reduction-rules-are-important"></a>Perché le regole di riduzione della superficie di attacco sono importanti

La superficie di attacco dell'organizzazione include tutte le posizioni in cui un utente malintenzionato potrebbe compromettere i dispositivi o le reti dell'organizzazione. Ridurre la superficie di attacco significa proteggere i dispositivi e la rete dell'organizzazione, lasciando agli utenti malintenzionati meno modi per eseguire attacchi. La configurazione delle regole di riduzione della superficie di attacco in Microsoft Defender for Endpoint può essere utile.

Le regole di riduzione della superficie di attacco sono mirate a determinati comportamenti software, ad esempio:

- Avvio di file eseguibili e script che tentano di scaricare o eseguire file
- Esecuzione di script offuscati o comunque sospetti
- Esecuzione di comportamenti che le app in genere non avviano durante il normale lavoro quotidiano

Tali comportamenti software sono talvolta visibili nelle applicazioni legittime. Tuttavia, questi comportamenti sono spesso considerati rischiosi perché vengono comunemente maltrattati da utenti malintenzionati tramite malware. Le regole di riduzione della superficie di attacco possono vincolare i comportamenti rischiosi basati su software e contribuire a proteggere l'organizzazione.

Per ulteriori informazioni sulla configurazione delle regole di riduzione della superficie di [attacco,](enable-attack-surface-reduction.md)vedere Enable attack surface reduction rules .

## <a name="assess-rule-impact-before-deployment"></a>Valutare l'impatto delle regole prima della distribuzione

È possibile valutare l'impatto di una regola di riduzione della superficie di attacco sulla rete aprendo il suggerimento per la sicurezza per tale regola in [gestione di minacce e vulnerabilità](/windows/security/threat-protection/#tvm).

:::image type="content" source="images/asrrecommendation.png" alt-text="Sicurezza per la regola di riduzione della superficie di attacco":::

Nel riquadro dei dettagli dei suggerimenti controlla l'impatto dell'utente per determinare quale percentuale dei dispositivi può accettare un nuovo criterio che abilita la regola in modalità di blocco senza influire negativamente sulla produttività.

Vedi [Requisiti nell'articolo](enable-attack-surface-reduction.md#requirements) "Abilitare le regole di riduzione della superficie di attacco" per informazioni sui sistemi operativi supportati e informazioni aggiuntive sui requisiti.

## <a name="audit-mode-for-evaluation"></a>Modalità di controllo per la valutazione

Usa [la modalità di controllo](audit-windows-defender.md) per valutare in che modo le regole di riduzione della superficie di attacco influirebbero sull'organizzazione, se abilitata. Eseguire prima tutte le regole in modalità di controllo per comprendere in che modo influiscono sulle applicazioni line-of-business. Molte applicazioni line-of-business sono scritte con problemi di sicurezza limitati e potrebbero eseguire attività in modi simili al malware. Monitorando i dati di controllo e [aggiungendo esclusioni](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) per le applicazioni necessarie, è possibile distribuire regole di riduzione della superficie di attacco senza ridurre la produttività.

## <a name="warn-mode-for-users"></a>Modalità avviso per gli utenti

(**NEW**!) Prima delle funzionalità della modalità di avviso, le regole di riduzione della superficie di attacco abilitate possono essere impostate sulla modalità di controllo o di blocco. Con la nuova modalità di avviso, ogni volta che il contenuto viene bloccato da una regola di riduzione della superficie di attacco, gli utenti visualizzano una finestra di dialogo che indica che il contenuto è bloccato. La finestra di dialogo offre inoltre all'utente un'opzione per sbloccare il contenuto. L'utente può quindi ritentare l'azione e l'operazione viene completata. Quando un utente sblocca il contenuto, il contenuto rimane sbloccato per 24 ore e quindi il blocco riprende.

La modalità avviso consente all'organizzazione di disporre di regole di riduzione della superficie di attacco senza impedire agli utenti di accedere al contenuto necessario per eseguire le proprie attività.

### <a name="requirements-for-warn-mode-to-work"></a>Requisiti per il funzionamento della modalità avviso

La modalità avviso è supportata nei dispositivi che eseguono le seguenti versioni di Windows:

- [Windows 10, versione 1809](/windows/whats-new/whats-new-windows-10-version-1809) o versioni successive
- [Windows Server, versione 1809](/windows-server/get-started/whats-new-in-windows-server-1809) o successiva

Antivirus Microsoft Defender deve essere in esecuzione con protezione in tempo reale in [modalità attiva.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)

Assicurarsi inoltre che siano [installati Antivirus Microsoft Defender e antimalware.](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)

- Requisito minimo di rilascio della piattaforma: `4.18.2008.9`
- Requisito minimo di rilascio del motore: `1.1.17400.5`

Per ulteriori informazioni e per ottenere gli aggiornamenti, vedere [Update for Microsoft Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform).

### <a name="cases-where-warn-mode-is-not-supported"></a>Casi in cui la modalità avviso non è supportata

La modalità avviso non è supportata per tre regole di riduzione della superficie di attacco quando le si configura in Microsoft Endpoint Manager. Se usi Criteri di gruppo per configurare le regole di riduzione della superficie di attacco, la modalità avviso è supportata. Le tre regole che non supportano la modalità di avviso quando vengono configurate in Microsoft Endpoint Manager sono le seguenti:

- [Impedire a JavaScript o VBScript di avviare il contenuto eseguibile](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) scaricato (GUID) `d3e037e1-3eb8-44c8-a917-57927947596d`
- [Bloccare la persistenza tramite la sottoscrizione di eventi WMI](#block-persistence-through-wmi-event-subscription) (GUID) `e6db77e5-3df2-4cf1-b95a-636979351e5b`
- [Usare la protezione avanzata contro ransomware](#use-advanced-protection-against-ransomware) (GUID) `c1db55ab-c21a-4637-bb3f-a12568109d35`

Inoltre, la modalità avviso non è supportata nei dispositivi che eseguono versioni precedenti di Windows. In questi casi, le regole di riduzione della superficie di attacco configurate per l'esecuzione in modalità avviso verranno eseguite in modalità blocco.

## <a name="notifications-and-alerts"></a>Notifiche e avvisi

Ogni volta che viene attivata una regola di riduzione della superficie di attacco, viene visualizzata una notifica nel dispositivo. È possibile [personalizzare la notifica](customize-attack-surface-reduction.md#customize-the-notification) con i dettagli aziendali e le informazioni sul contatto.

Inoltre, quando vengono attivate determinate regole di riduzione della superficie di attacco, vengono generati avvisi.

Le notifiche e gli avvisi generati possono essere visualizzati nel portale di Microsoft 365 Defender ( ) (in precedenza [https://security.microsoft.com](https://security.microsoft.com) denominato [Microsoft Defender Security Center](microsoft-defender-security-center.md)).

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a>Eventi avanzati di ricerca e riduzione della superficie di attacco

Puoi usare la ricerca avanzata per visualizzare gli eventi di riduzione della superficie di attacco. Per semplificare il volume dei dati in arrivo, solo i processi univoci per ogni ora sono visualizzabili con la ricerca avanzata. L'ora di un evento di riduzione della superficie di attacco è la prima volta che l'evento viene visualizzato entro l'ora.

Si supponga, ad esempio, che si verifichi un evento di riduzione della superficie di attacco su 10 dispositivi durante le 14.00. Si supponga che il primo evento si sia verificato alle 2:15 e l'ultimo alle 2:45. Con la ricerca avanzata, vedrai un'istanza di tale evento (anche se in realtà si è verificato su 10 dispositivi) e il timestamp sarà 14:15.

Per ulteriori informazioni sulla ricerca avanzata, vedere Ricerca proattiva [per le minacce con la ricerca avanzata.](advanced-hunting-overview.md)

## <a name="attack-surface-reduction-features-across-windows-versions"></a>Funzionalità di riduzione della superficie di attacco Windows versioni

Puoi impostare regole di riduzione della superficie di attacco per i dispositivi che eseguono una delle seguenti edizioni e versioni di Windows:

- Windows 10 Pro versione [1709](/windows/whats-new/whats-new-windows-10-version-1709) o successiva
- Windows 10 Enterprise versione [1709](/windows/whats-new/whats-new-windows-10-version-1709) o successiva
- Windows Server, [versione 1803 (Canale semestraale)](/windows-server/get-started/whats-new-in-windows-server-1803) o versione successiva
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Anche se le regole di riduzione della superficie di attacco non richiedono una licenza [Windows E5,](/windows/deployment/deploy-enterprise-licenses)se si dispone di Windows E5, si ottengono funzionalità di gestione avanzate. Le funzionalità avanzate, disponibili solo in Windows E5, includono:

- Monitoraggio, analisi e flussi di lavoro disponibili in [Defender for Endpoint](microsoft-defender-endpoint.md)
- Funzionalità di creazione di report e configurazione [in Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).

Queste funzionalità avanzate non sono disponibili con una licenza Windows Professional o Windows E3. Tuttavia, se si dispone di tali licenze, è possibile utilizzare visualizzatore eventi e registri Antivirus Microsoft Defender per esaminare gli eventi delle regole di riduzione della superficie di attacco.

## <a name="review-attack-surface-reduction-events-in-the-microsoft-365-defender-portal"></a>Esaminare gli eventi di riduzione della superficie di attacco nel portale Microsoft 365 Defender di attacco

Defender for Endpoint fornisce report dettagliati per eventi e blocchi nell'ambito di scenari di analisi degli avvisi.

Puoi eseguire query su Defender per i dati [dell'endpoint](microsoft-defender-security-center.md) in Microsoft 365 Defender tramite [ricerca avanzata.](advanced-hunting-query-language.md) Se si esegue la modalità [di](audit-windows-defender.md)controllo, è possibile utilizzare la ricerca avanzata per comprendere in che modo le regole di riduzione della superficie di attacco potrebbero influire sull'ambiente.

Ecco un esempio di query:

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>Esaminare gli eventi di riduzione della superficie di attacco nel Visualizzatore Windows eventi

È possibile esaminare il registro eventi Windows eventi per visualizzare gli eventi generati dalle regole di riduzione della superficie di attacco:

1. Scarica il [pacchetto di valutazione](https://aka.ms/mp7z2w) ed estrai il file *cfa-events.xml* in un percorso facilmente accessibile nel dispositivo.

2. Immettere le parole *Visualizzatore eventi* nel menu Start per aprire il Visualizzatore Windows eventi.

3. In **Azioni** selezionare **Importa visualizzazione personalizzata...**.

4. Selezionare *l'cfa-events.xml* file da cui è stato estratto. In alternativa, [copiare il codice XML direttamente](event-views.md).

5. Selezionare **OK**.

È possibile creare una visualizzazione personalizzata che filtra gli eventi in modo da visualizzare solo gli eventi seguenti, tutti correlati all'accesso controllato alle cartelle:

|ID evento|Descrizione|
|---|---|
|5007|Evento quando vengono modificate le impostazioni|
|1121|Evento quando la regola viene attivata in modalità blocco|
|1122|Evento quando la regola viene attivata in modalità di controllo|

La "versione del motore" elencata per gli eventi di riduzione della superficie di attacco nel registro eventi, viene generata da Defender per Endpoint, non dal sistema operativo. Defender for Endpoint è integrato con Windows 10, quindi questa funzionalità funziona su tutti i dispositivi Windows 10 installati.

## <a name="attack-surface-reduction-rules"></a>Regole per la riduzione della superficie di attacco

La tabella e le sottosezioni seguenti descrivono ognuna delle 16 regole di riduzione della superficie di attacco. Le regole di riduzione della superficie di attacco sono elencate in ordine alfabetico, in base al nome della regola.

Se si configurano regole di riduzione della superficie di attacco tramite Criteri di gruppo o PowerShell, sono necessari i GUID. D'altra parte, se si utilizza Microsoft Endpoint Manager o Microsoft Intune, non sono necessari i GUID.

|Nome della regola|GUID|Esclusioni di & file|Sistema operativo minimo supportato|
|---|:---:|---|---|
|[Bloccare l'abuso di driver firmati vulnerabili sfruttati](#block-abuse-of-exploited-vulnerable-signed-drivers)|`56a863a9-875e-4185-98a7-b882c64b5ce5`|Supportato|[Windows 10 versione 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) o successiva) |
|[Impedire ad Adobe Reader di creare processi figlio](#block-adobe-reader-from-creating-child-processes)|`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`|Supportato|[Windows 10 versione 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) o successiva|
|[Impedire a Office applicazioni di creare processi figlio](#block-all-office-applications-from-creating-child-processes)|`D4F940AB-401B-4EFC-AADC-AD5F3C50688A`|Supportato|[Windows 10 versione 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) o successiva|
|[Bloccare il furto delle credenziali dal sottosistema Windows autorità di sicurezza locale (lsass.exe)](#block-credential-stealing-from-the-windows-local-security-authority-subsystem)|`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`|Supportato|[Windows 10 versione 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) o successiva|
|[Bloccare il contenuto eseguibile dal client di posta elettronica e dalla webmail](#block-executable-content-from-email-client-and-webmail)|`BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`|Supportato|[Windows 10 versione 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) o successiva|
|[Bloccare l'esecuzione dei file eseguibili a meno che non soddisfino un criterio di prevalenza, età o elenco attendibile](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)|`01443614-cd74-433a-b99e-2ecdc07bfc25`|Supportato|[Windows 10 versione 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) o successiva|
|[Bloccare l'esecuzione di script potenzialmente offuscati](#block-execution-of-potentially-obfuscated-scripts)|`5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`|Supportato|[Windows 10 versione 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) o successiva|
|[Impedire a JavaScript o VBScript di avviare il contenuto eseguibile scaricato](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)|`D3E037E1-3EB8-44C8-A917-57927947596D`|Supportato|[Windows 10 versione 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) o successiva|
|[Impedire Office applicazioni di creare contenuto eseguibile](#block-office-applications-from-creating-executable-content)|`3B576869-A4EC-4529-8536-B80A7769E899`|Supportato|[Windows 10 versione 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) o successiva|
|[Bloccare Office applicazioni dall'inserimento di codice in altri processi](#block-office-applications-from-injecting-code-into-other-processes)|`75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`|Supportato|[Windows 10 versione 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) o successiva|
|[Impedire Office'applicazione di comunicazione di creare processi figlio](#block-office-communication-application-from-creating-child-processes)|`26190899-1602-49e8-8b27-eb1d0a1ce869`|Supportato|[Windows 10 versione 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) o successiva|
|[Bloccare la persistenza tramite la sottoscrizione di eventi WMI](#block-persistence-through-wmi-event-subscription)|`e6db77e5-3df2-4cf1-b95a-636979351e5b`|Non supportato|[Windows 10 versione 1903](/windows/whats-new/whats-new-windows-10-version-1903) (build 18362) o successiva|
|[Bloccare le creazioni di processi originate dai comandi PSExec e WMI](#block-process-creations-originating-from-psexec-and-wmi-commands)|`d1e49aac-8f56-4280-b9ba-993a6d77406c`|Supportato|[Windows 10 versione 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) o successiva|
|[Bloccare i processi non attendibili e non firmati eseguiti da USB](#block-untrusted-and-unsigned-processes-that-run-from-usb)|`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`|Supportato|[Windows 10 versione 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) o successiva|
|[Bloccare le chiamate API Win32 Office macro](#block-win32-api-calls-from-office-macros)|`92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`|Supportato|[Windows 10 versione 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) o successiva|
|[Usare la protezione avanzata contro ransomware](#use-advanced-protection-against-ransomware)|`c1db55ab-c21a-4637-bb3f-a12568109d35`|Supportato|[Windows 10 versione 1709](/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) o successiva|

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a>Bloccare l'abuso di driver firmati vulnerabili sfruttati

Questa regola impedisce a un'applicazione di scrivere un driver firmato vulnerabile su disco. I driver firmati vulnerabili possono essere sfruttati da applicazioni locali che dispongono di privilegi sufficienti per accedere \-  \- al kernel. I driver firmati vulnerabili consentono agli utenti malintenzionati di disabilitare o aggirare le soluzioni di sicurezza, causando una compromissione del sistema.

La **regola Blocca l'abuso dei** driver firmati vulnerabili sfruttati non blocca il caricamento di un driver già esistente nel sistema.

>[!NOTE]
>
> Puoi configurare questa regola usando [l'URI OMA MEM](enable-attack-surface-reduction.md#mem) per le informazioni procedurali sulle regole personalizzate URI OMA MEM.
>
> È inoltre possibile configurare questa regola utilizzando [PowerShell.](enable-attack-surface-reduction.md#powershell)
>
> Per fare in modo che un driver sia esaminato, utilizzare questo sito Web per [inviare un driver per l'analisi.](https://www.microsoft.com/en-us/wdsi/driversubmission)

Sistemi operativi supportati:

- [Windows 10 Pro versione 1709](/windows/whats-new/whats-new-windows-10-version-1709) o successiva
- [Windows 10 Enterprise versione 1709](/windows/whats-new/whats-new-windows-10-version-1709) o successiva
- [Windows Server, versione 1803 (Canale semestraale)](/windows-server/get-started/whats-new-in-windows-server-1803) o versione successiva
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Nome Intune: `Block abuse of exploited vulnerable signed drivers`

GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`

### <a name="block-adobe-reader-from-creating-child-processes"></a>Impedire ad Adobe Reader di creare processi figlio

Questa regola impedisce gli attacchi bloccando La creazione di processi da parte di Adobe Reader.

Tramite social engineering o exploit, il malware può scaricare e avviare payload ed uscire da Adobe Reader. Bloccando la generazione dei processi figlio da Parte di Adobe Reader, il malware che tenta di usarlo come vettore non è in grado di diffondersi.

Sistemi operativi supportati:

- [Windows 10, versione 1809](/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows Server, versione 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Nome Intune: `Process creation from Adobe Reader (beta)`

Nome di Configuration Manager: Non ancora disponibile

GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`

### <a name="block-all-office-applications-from-creating-child-processes"></a>Impedire a Office applicazioni di creare processi figlio

Questa regola impedisce Office app di creare processi figlio. Office app includono Word, Excel, PowerPoint, OneNote e Access.

La creazione di processi figlio dannosi è una strategia antimalware comune. I malware che Office come vettore spesso eseguono macro VBA e sfruttano il codice per scaricare e tentare di eseguire più payload. Tuttavia, alcune applicazioni line-of-business legittime potrebbero anche generare processi figlio per scopi benigni. ad esempio la generazione di un prompt dei comandi o l'uso di PowerShell per configurare le impostazioni del Registro di sistema.

Sistemi operativi supportati:

- [Windows 10, versione 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, versione 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Nome Intune: `Office apps launching child processes`

Nome di Configuration Manager: `Block Office application from creating child processes`

GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a>Bloccare il furto delle credenziali dal sottosistema Windows'autorità di sicurezza locale

Questa regola consente di impedire il furto delle credenziali bloccando il servizio LSASS (Local Security Authority Subsystem Service).

LSASS autentica gli utenti che a loro Windows computer. Microsoft Defender Credential Guard in Windows 10 in genere impedisce i tentativi di estrarre le credenziali da LSASS. Tuttavia, alcune organizzazioni non possono abilitare Credential Guard in tutti i computer a causa di problemi di compatibilità con driver smart card personalizzati o altri programmi caricati nell'Autorità di sicurezza locale (LSA). In questi casi, gli utenti malintenzionati possono usare strumenti di hacking come Mimikatz per raschiare password non crittografate e hash NTLM da LSASS.

> [!NOTE]
> In alcune app, il codice enumera tutti i processi in esecuzione e tenta di aprirli con autorizzazioni esaustivi. Questa regola nega l'azione di apertura del processo dell'app e registra i dettagli nel registro eventi di sicurezza. Questa regola può generare molto rumore. Se hai un'app che enumera semplicemente LSASS, ma non ha alcun impatto reale sulle funzionalità, non è necessario aggiungerla all'elenco di esclusione. Di per sé, questa voce del registro eventi non indica necessariamente una minaccia dannosa.

Sistemi operativi supportati:

- [Windows 10, versione 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, versione 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Nome Intune: `Flag credential stealing from the Windows local security authority subsystem`

Nome di Configuration Manager: `Block credential stealing from the Windows local security authority subsystem`

GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`

### <a name="block-executable-content-from-email-client-and-webmail"></a>Bloccare il contenuto eseguibile dal client di posta elettronica e dalla webmail

Questa regola impedisce l'avvio dei seguenti tipi di file dalla posta elettronica aperta all'interno dell'applicazione Microsoft Outlook o Outlook.com e da altri provider di webmail popolari:

- File eseguibili (ad esempio .exe, .dll o scr)
- File di script (ad esempio un file con estensione ps, Visual Basic .vbs o JavaScript .js)

Sistemi operativi supportati:

- [Windows 10, versione 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, versione 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Microsoft Endpoint Manager CB 1710](/configmgr/core/servers/manage/updates)

Nome Intune: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`

Microsoft Endpoint Manager nome:`Block executable content from email client and webmail`

GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`

> [!NOTE]
> La regola **Blocca il contenuto eseguibile dal client di** posta elettronica e dalla webmail presenta le descrizioni alternative seguenti, a seconda dell'applicazione utilizzata:
>
> - Intune (profili di configurazione): esecuzione del contenuto eseguibile (exe, dll, ps, js, vbs e così via) eliminata dalla posta elettronica (webmail/client di posta) (nessuna eccezione).
> - Endpoint Manager: bloccare il download del contenuto eseguibile dai client di posta elettronica e webmail.
> - Criteri di gruppo: bloccare il contenuto eseguibile dal client di posta elettronica e dalla webmail.

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a>Bloccare l'esecuzione dei file eseguibili a meno che non soddisfino un criterio di prevalenza, età o elenco attendibile

Questa regola blocca l'avvio dei file eseguibili, ad esempio .exe, .dll o scr, a meno che non vengano soddisfatte le condizioni seguenti:

- Prevalenza: i file eseguibili si trovano in più di 1.000 endpoint
- Età: i file eseguibili sono stati rilasciati più di 24 ore fa
- Percorso: i file eseguibili sono inclusi in un elenco attendibile o in un elenco di esclusione

L'avvio di file eseguibili non attendibili o sconosciuti può essere rischioso, poiché inizialmente potrebbe non essere chiaro se i file sono dannosi.

> [!IMPORTANT]
> Per usare [questa regola, è necessario](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) abilitare la protezione recapitata nel cloud.
>
> La regola **Blocca l'esecuzione dei** file eseguibili a meno che non soddisfino un criterio di prevalenza, età o elenco attendibile con GUID sia di proprietà di Microsoft e non sia specificato `01443614-cd74-433a-b99e-2ecdc07bfc25` dagli amministratori. Questa regola usa la protezione recapitata nel cloud per aggiornare regolarmente l'elenco attendibile.
>
> È possibile specificare singoli file o cartelle (utilizzando percorsi di cartelle o nomi di risorse completi), ma non è possibile specificare a quali regole o esclusioni si applicano.

Sistemi operativi supportati:

- [Windows 10, versione 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, versione 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Nome Intune: `Executables that don't meet a prevalence, age, or trusted list criteria`

Nome di Configuration Manager: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`

GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`

### <a name="block-execution-of-potentially-obfuscated-scripts"></a>Bloccare l'esecuzione di script potenzialmente offuscati

Questa regola rileva le proprietà sospette all'interno di uno script offuscato.

L'offuscamento degli script è una tecnica comune utilizzata dagli autori di malware e dalle applicazioni legittime per nascondere la proprietà intellettuale o ridurre i tempi di caricamento degli script. Gli autori di malware usano anche l'offuscamento per rendere più difficile la lettura di codice dannoso, impedendo così un'attenta analisi da parte degli utenti e del software di sicurezza.

Sistemi operativi supportati:

- [Windows 10, versione 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, versione 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Nome Intune: `Obfuscated js/vbs/ps/macro code`

Nome di Configuration Manager: `Block execution of potentially obfuscated scripts`

GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a>Impedire a JavaScript o VBScript di avviare il contenuto eseguibile scaricato

Questa regola impedisce agli script di avviare contenuti scaricati potenzialmente dannosi. Il malware scritto in JavaScript o VBScript spesso funge da downloader per recuperare e avviare altro malware da Internet.

Anche se non è comune, le applicazioni line-of-business a volte usano script per scaricare e avviare programmi di installazione.

Sistemi operativi supportati:

- [Windows 10, versione 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, versione 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Nome Intune: `js/vbs executing payload downloaded from Internet (no exceptions)`

Nome di Configuration Manager: `Block JavaScript or VBScript from launching downloaded executable content`

GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`

### <a name="block-office-applications-from-creating-executable-content"></a>Impedire Office applicazioni di creare contenuto eseguibile

Questa regola impedisce alle app Office, tra cui Word, Excel e PowerPoint, di creare contenuti eseguibili potenzialmente dannosi, bloccando la scrittura su disco di codice dannoso.

Il malware che Office come vettore potrebbe tentare di uscire dall'Office e salvare componenti dannosi su disco. Questi componenti dannosi sarebbero sopravvissuti al riavvio del computer e persistessero nel sistema. Pertanto, questa regola si difende da una tecnica di persistenza comune.

Sistemi operativi supportati:

- [Windows 10, versione 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, versione 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [System Center Configuration Manager](/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM è ora Microsoft Endpoint Configuration Manager)

Nome Intune: `Office apps/macros creating executable content`

Nome SCCM: `Block Office applications from creating executable content`

GUID: `3B576869-A4EC-4529-8536-B80A7769E899`

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a>Bloccare Office applicazioni dall'inserimento di codice in altri processi

Questa regola blocca i tentativi di inserimento del codice Office app in altri processi.

Gli utenti malintenzionati potrebbero tentare di usare app Office per eseguire la migrazione di codice dannoso in altri processi tramite l'inserimento di codice, in modo che il codice possa mascherarsi come processo pulito.

Non esistono scopi aziendali legittimi noti per l'uso dell'inserimento di codice.

Questa regola si applica a Word, Excel e PowerPoint.

Sistemi operativi supportati:

- [Windows 10, versione 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, versione 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Nome Intune: `Office apps injecting code into other processes (no exceptions)`

Nome di Configuration Manager: `Block Office applications from injecting code into other processes`

GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`

### <a name="block-office-communication-application-from-creating-child-processes"></a>Impedire Office'applicazione di comunicazione di creare processi figlio

Questa regola impedisce Outlook di creare processi figlio, pur consentendo funzioni Outlook legittimi.

Questa regola protegge dagli attacchi di social engineering e impedisce allo sfruttamento del codice di sfruttare le vulnerabilità in Outlook. Protegge inoltre dalle regole Outlook e dagli [exploit](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) dei moduli che gli utenti malintenzionati possono utilizzare quando le credenziali di un utente vengono compromesse.

> [!NOTE]
> Questa regola blocca le descrizioni comandi e le descrizioni comandi dei criteri DLP in Outlook. Questa regola si applica solo Outlook e Outlook.com.

Sistemi operativi supportati:

- [Windows 10, versione 1809](/windows/whats-new/whats-new-windows-10-version-1809)
- [Windows Server, versione 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Nome Intune: `Process creation from Office communication products (beta)`

Nome di Configuration Manager: Non disponibile

GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`

### <a name="block-persistence-through-wmi-event-subscription"></a>Bloccare la persistenza tramite la sottoscrizione di eventi WMI

Questa regola impedisce al malware di abusare di WMI per ottenere la persistenza in un dispositivo.

> [!IMPORTANT]
> Le esclusioni di file e cartelle non si applicano a questa regola di riduzione della superficie di attacco.

Le minacce senza file utilizzano diverse tattiche per rimanere nascoste, per evitare di essere visibili nel file system e per ottenere il controllo periodico dell'esecuzione. Alcune minacce possono usare in modo improprio l'archivio WMI e il modello di eventi per rimanere nascosti.

Sistemi operativi supportati:

- [Windows 10, versione 1903](/windows/whats-new/whats-new-windows-10-version-1903)
- [Windows Server 1903](/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

Nome Intune: Non disponibile

Nome di Configuration Manager: Non disponibile

GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a>Bloccare le creazioni di processi originate dai comandi PSExec e WMI

Questa regola blocca l'esecuzione dei processi creati [tramite PsExec](/sysinternals/downloads/psexec) [e WMI.](/windows/win32/wmisdk/about-wmi) Sia PsExec che WMI possono eseguire codice in remoto, quindi esiste il rischio che malware abuso di questa funzionalità a scopo di comando e controllo o per diffondere un'infezione in tutta la rete di un'organizzazione.

> [!WARNING]
> Usa questa regola solo se gestisci i dispositivi con [Intune](/intune) o un'altra soluzione MDM. Questa regola non è compatibile con la gestione [tramite Microsoft Endpoint Configuration Manager](/configmgr) perché questa regola blocca i comandi WMI utilizzati dal client di Configuration Manager per funzionare correttamente.

Sistemi operativi supportati:

- [Windows 10, versione 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, versione 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Nome Intune: `Process creation from PSExec and WMI commands`

Nome di Configuration Manager: Non applicabile

GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a>Bloccare i processi non attendibili e non firmati eseguiti da USB

Con questa regola, gli amministratori possono impedire l'esecuzione di file eseguibili non firmati o non attendibili da unità rimovibili USB, incluse le schede SD. I tipi di file bloccati includono file eseguibili (ad esempio .exe, .dll o scr)

Sistemi operativi supportati:

- [Windows 10, versione 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, versione 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Nome Intune: `Untrusted and unsigned processes that run from USB`

Nome di Configuration Manager: `Block untrusted and unsigned processes that run from USB`

GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`

### <a name="block-win32-api-calls-from-office-macros"></a>Bloccare le chiamate API Win32 Office macro

Questa regola impedisce alle macro VBA di chiamare le API Win32.

Office VBA abilita le chiamate API Win32. Il malware può usare in modo improprio questa funzionalità, ad esempio chiamare le [API Win32](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) per avviare shellcode dannosi senza scrivere nulla direttamente sul disco. La maggior parte delle organizzazioni non si basa sulla possibilità di chiamare le API Win32 nel funzionamento quotidiano, anche se usano macro in altri modi.

Sistemi operativi supportati:

- [Windows 10, versione 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows Server, versione 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Nome Intune: `Win32 imports from Office macro code`

Nome di Configuration Manager: `Block Win32 API calls from Office macros`

GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`

### <a name="use-advanced-protection-against-ransomware"></a>Usare la protezione avanzata contro ransomware

Questa regola fornisce un ulteriore livello di protezione contro i ransomware. Usa sia l'euristica client che l'euristica cloud per determinare se un file è simile a ransomware. Questa regola non blocca i file con una o più delle caratteristiche seguenti:

- Il file è già stato trovato illeso nel cloud Microsoft.
- Il file è un file firmato valido.
- Il file è abbastanza diffuso da non essere considerato ransomware.

La regola tende a errare sul lato della cautela per evitare ransomware.

> [!NOTE]
> Per usare [questa regola, è necessario](enable-cloud-protection-microsoft-defender-antivirus.md) abilitare la protezione recapitata nel cloud.

Sistemi operativi supportati:

- [Windows 10, versione 1803](/windows/whats-new/whats-new-windows-10-version-1803)
- [Windows Server, versione 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)

Nome Intune: `Advanced ransomware protection`

Nome di Configuration Manager: `Use advanced protection against ransomware`

GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`
